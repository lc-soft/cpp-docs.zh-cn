---
title: ferror
ms.date: 11/04/2016
api_name:
- ferror
api_location:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-stdio-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- ferror
helpviewer_keywords:
- ferror function
- streams, testing for errors
- errors [C++], testing for stream
ms.assetid: 528a34bc-f2aa-4c3f-b89a-5b148e6864f7
ms.openlocfilehash: 4efb1b01ac94f1cb2d28bffb1f09b594a0e71479
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2019
ms.locfileid: "70941104"
---
# <a name="ferror"></a>ferror

测试流中的错误。

## <a name="syntax"></a>语法

```C
int ferror(
   FILE *stream
);
```

### <a name="parameters"></a>参数

*stream*<br/>
指向**文件**结构的指针。

## <a name="return-value"></a>返回值

如果*流*中未发生错误，则**ferror**将返回0。 否则，返回一个非零值。 如果 stream 为**NULL**， **ferror**将调用无效参数处理程序，如[参数验证](../../c-runtime-library/parameter-validation.md)中所述。 如果允许执行继续, 则此函数会将**errno**设置为**EINVAL** , 并返回0。

有关这些代码以及其他错误代码的详细信息，请参阅 [_doserrno、errno、_sys_errlist 和 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)。

## <a name="remarks"></a>备注

**Ferror**例程（作为函数和宏实现）测试与*stream*关联的文件的读取或写入错误。 如果发生错误，则流的错误指示符将保留设置，直到关闭或回退流，或直到对其调用**clearerr** 。

## <a name="requirements"></a>要求

|函数|必需的标头|
|--------------|---------------------|
|**ferror**|\<stdio.h>|

有关其他兼容性信息，请参阅 [兼容性](../../c-runtime-library/compatibility.md)。

## <a name="example"></a>示例

请参阅 [feof](feof.md) 的示例。

## <a name="see-also"></a>请参阅

[错误处理](../../c-runtime-library/error-handling-crt.md)<br/>
[流 I/O](../../c-runtime-library/stream-i-o.md)<br/>
[clearerr](clearerr.md)<br/>
[_eof](eof.md)<br/>
[feof](feof.md)<br/>
[fopen、_wfopen_wfopen](fopen-wfopen.md)<br/>
[perror、_wperror](perror-wperror.md)<br/>
