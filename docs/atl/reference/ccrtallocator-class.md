---
title: CCRTAllocator 类
ms.date: 11/04/2016
f1_keywords:
- CCRTAllocator
- ATLCORE/ATL::CCRTAllocator
- ATLCORE/ATL::CCRTAllocator::Allocate
- ATLCORE/ATL::CCRTAllocator::Free
- ATLCORE/ATL::CCRTAllocator::Reallocate
helpviewer_keywords:
- CCRTAllocator class
ms.assetid: 3e1b8cb0-859a-41ab-8e93-6f0b5ceca49d
ms.openlocfilehash: c08d594e1c0f4d532f46961e266bf6ced98c51b2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62259074"
---
# <a name="ccrtallocator-class"></a>CCRTAllocator 类

此类提供用于管理内存使用的内存 CRT 例程的方法。

## <a name="syntax"></a>语法

```
class ATL::CCRTAllocator
```

## <a name="members"></a>成员

### <a name="public-methods"></a>公共方法

|名称|描述|
|----------|-----------------|
|[CCRTAllocator::Allocate](#allocate)|（静态）调用此方法来分配内存。|
|[CCRTAllocator::Free](#free)|（静态）调用此方法来释放内存。|
|[CCRTAllocator::Reallocate](#reallocate)|（静态）调用此方法以重新分配内存。|

## <a name="remarks"></a>备注

使用此类[CHeapPtr](../../atl/reference/cheapptr-class.md)提供 CRT 内存分配例程。 与类[CComAllocator](../../atl/reference/ccomallocator-class.md)，提供了使用 COM 例程的相同方法。

## <a name="requirements"></a>要求

**标头：** atlcore.h

##  <a name="allocate"></a>  CCRTAllocator::Allocate

调用此静态函数以分配内存。

```
static __declspec(allocator) void* Allocate(size_t nBytes) throw();
```

### <a name="parameters"></a>参数

*nBytes*<br/>
要分配的字节数。

### <a name="return-value"></a>返回值

返回指向已分配空间的 void 指针；如果可用内存不足，则返回 NULL。

### <a name="remarks"></a>备注

分配内存。 请参阅[malloc](../../c-runtime-library/reference/malloc.md)的更多详细信息。

##  <a name="free"></a>  CCRTAllocator::Free

调用此静态函数以释放内存。

```
static void Free(void* p) throw();
```

### <a name="parameters"></a>参数

*p*<br/>
指向已分配内存的指针。

### <a name="remarks"></a>备注

释放已分配的内存。 请参阅[免费](../../c-runtime-library/reference/free.md)的更多详细信息。

##  <a name="reallocate"></a>  CCRTAllocator::Reallocate

调用此静态函数以重新分配内存。

```
static __declspec(allocator) void* Reallocate(void* p, size_t nBytes) throw();
```

### <a name="parameters"></a>参数

*p*<br/>
指向已分配内存的指针。

*nBytes*<br/>
要重新分配的字节数。

### <a name="return-value"></a>返回值

如果没有足够的内存，请返回指向已分配空间的 void 指针，或返回 NULL。

### <a name="remarks"></a>备注

调整已分配内存的大小。 请参阅[realloc](../../c-runtime-library/reference/realloc.md)的更多详细信息。

## <a name="see-also"></a>请参阅

[CHeapPtr 类](../../atl/reference/cheapptr-class.md)<br/>
[CComAllocator 类](../../atl/reference/ccomallocator-class.md)<br/>
[类概述](../../atl/atl-class-overview.md)
