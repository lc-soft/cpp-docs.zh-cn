---
title: strtol、wcstol、_strtol_l、_wcstol_l
ms.date: 11/04/2016
api_name:
- strtol
- wcstol
- _strtol_l
- _wcstol_l
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
- api-ms-win-crt-convert-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _wcstol_l
- strtol
- _tcstol
- wcstol
- _strtol_l
- _tcstol_l
helpviewer_keywords:
- wcstol function
- wcstol_l function
- _tcstol function
- string conversion, to integers
- tcstol function
- strtol_l function
- _wcstol_l function
- _strtol_l function
- strtol function
ms.assetid: 1787c96a-f283-4a83-9325-33cfc1c7e240
ms.openlocfilehash: b40362e93a41730e46ad0911b5a633118d024e9c
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2019
ms.locfileid: "70957637"
---
# <a name="strtol-wcstol-_strtol_l-_wcstol_l"></a>strtol、wcstol、_strtol_l、_wcstol_l

将字符串转换为长整数值。

## <a name="syntax"></a>语法

```C
long strtol(
   const char *strSource,
   char **endptr,
   int base
);
long wcstol(
   const wchar_t *strSource,
   wchar_t **endptr,
   int base
);
long _strtol_l(
   const char *strSource,
   char **endptr,
   int base,
   _locale_t locale
);
long _wcstol_l(
   const wchar_t *strSource,
   wchar_t **endptr,
   int base,
   _locale_t locale
);
```

### <a name="parameters"></a>参数

*strSource*<br/>
要转换的 null 终止的字符串。

*endptr*<br/>
指向停止扫描的字符的指针。

*base*<br/>
要使用的基数。

*locale*<br/>
要使用的区域设置。

## <a name="return-value"></a>返回值

**strtol**返回字符串*strSource*中表示的值，但表示形式会导致溢出，在这种情况下，它将返回**LONG_MAX**或**LONG_MIN**。 如果无法执行任何转换，则**strtol**将返回0。 **wcstol**将类似值返回到**strtol**。 对于这两个函数，如果出现溢出或下溢，则**errno**设置为**ERANGE** 。

有关这些代码以及其他返回代码的详细信息，请参阅 [_doserrno、errno、_sys_errlist 和 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)。

## <a name="remarks"></a>备注

**Strtol**函数将*strSource*转换为**long 类型**。 **strtol**停止读取其无法识别为数字一部分的第一个字符的字符串*strSource* 。 这可能是终止 null 字符，也可能是大于或等于*base*的第一个数字字符。

**wcstol**是**strtol**的宽字符版本;其*strSource*参数是宽字符字符串。 否则这些函数具有相同行为。

### <a name="generic-text-routine-mappings"></a>一般文本例程映射

|TCHAR.H 例程|未定义 _UNICODE 和 _MBCS|已定义 _MBCS|已定义 _UNICODE|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstol**|**strtol**|**strtol**|**wcstol**|
|**_tcstol_l**|**_strtol_l**|**_strtol_l**|**_wcstol_l**|

当前区域设置的**LC_NUMERIC**类别设置决定了*strSource*中的基数字符的识别;有关详细信息，请参阅[setlocale](setlocale-wsetlocale.md)。 不带 **_l**后缀的函数使用当前区域设置; **_strtol_l**和 **_wcstol_l**与没有 **_l**后缀的相应函数相同，只不过它们改用传入的区域设置。 有关详细信息，请参阅 [Locale](../../c-runtime-library/locale.md)。

如果*endptr*不为**NULL**，则指向停止扫描的字符的指针将存储在*endptr*指向的位置。 如果无法执行任何转换（未找到任何有效的数字或指定了无效的基数），则*strSource*的值将存储在*endptr*指向的位置。

**strtol**要求*strSource*指向以下格式的字符串：

> [*空格*][{ **+** &#124; &#124; &#124; }] [0 [{x x}]] [数字字母] **-**

*空格*可能包含被忽略的空格和制表符;*位数*为一个或多个十进制数字;*字母*是从 "a" 到 "z" （或 "a" 到 "z"）的一个或多个字母。  不符合此形式的第一个字符停止扫描。 如果*base*介于2和36之间，则将其用作数字的基数。 如果*base*为0，则使用*strSource*指向的字符串的初始字符来确定基。 如果第一个字符为 0，且第二个字符不为“x”或“X”，则将该字符串视为八进制整数。 如果第一个字符为“0”，且第二个字符为“x”或“X”，则将该字符串视为十六进制整数。 如果第一个字符是“1”至“9”，则将该字符串视为十进制整数。 为字母“a”到“z”（或“A”到“Z”）分配了 10 到 35 的值；仅允许分配的值小于 *base* 的字母。 超出基数范围的第一个字符停止扫描。 例如，如果*base*为0且扫描的第一个字符为 "0"，则假定八进制整数，且 "8" 或 "9" 字符会停止扫描。

## <a name="requirements"></a>要求

|例程所返回的值|必需的标头|
|-------------|---------------------|
|**strtol**|\<stdlib.h>|
|**wcstol**|\<stdlib.h> 或 \<wchar.h>|
|**_strtol_l**|\<stdlib.h>|

有关其他兼容性信息，请参阅 [兼容性](../../c-runtime-library/compatibility.md)。

## <a name="example"></a>示例

请参阅 [strtod](strtod-strtod-l-wcstod-wcstod-l.md) 的示例。

## <a name="see-also"></a>请参阅

[数据转换](../../c-runtime-library/data-conversion.md)<br/>
[区域设置](../../c-runtime-library/locale.md)<br/>
[localeconv](localeconv.md)<br/>
[setlocale、_wsetlocale](setlocale-wsetlocale.md)<br/>
[字符串到数值函数](../../c-runtime-library/string-to-numeric-value-functions.md)<br/>
[strtod、_strtod_l、wcstod、_wcstod_l](strtod-strtod-l-wcstod-wcstod-l.md)<br/>
[strtoul、_strtoul_l、wcstoul、_wcstoul_l](strtoul-strtoul-l-wcstoul-wcstoul-l.md)<br/>
[atof、_atof_l、_wtof、_wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
