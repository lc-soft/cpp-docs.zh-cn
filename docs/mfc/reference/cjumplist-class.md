---
title: "CJumpList 类 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CJumpList
- AFXADV/CJumpList
- AFXADV/CJumpList::CJumpList
- AFXADV/CJumpList::AbortList
- AFXADV/CJumpList::AddDestination
- AFXADV/CJumpList::AddKnownCategory
- AFXADV/CJumpList::AddTask
- AFXADV/CJumpList::AddTasks
- AFXADV/CJumpList::AddTaskSeparator
- AFXADV/CJumpList::ClearAll
- AFXADV/CJumpList::ClearAllDestinations
- AFXADV/CJumpList::CommitList
- AFXADV/CJumpList::GetDestinationList
- AFXADV/CJumpList::GetMaxSlots
- AFXADV/CJumpList::GetRemovedItems
- AFXADV/CJumpList::InitializeList
- AFXADV/CJumpList::SetAppID
dev_langs:
- C++
helpviewer_keywords:
- CJumpList class
ms.assetid: d364d27e-f512-4b12-9872-c2a17c78ab1f
caps.latest.revision: 15
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: b3662bd00f7c757df3a77f5920c48389bbd749fb
ms.contentlocale: zh-cn
ms.lasthandoff: 02/24/2017

---
# <a name="cjumplist-class"></a>CJumpList 类
一个`CJumpList`是右键单击任务栏中的图标上时显示的快捷方式的列表。  
  
## <a name="syntax"></a>语法  
  
```  
class CJumpList;  
```  
  
## <a name="members"></a>成员  
  
### <a name="public-constructors"></a>公共构造函数  
  
|名称|描述|  
|----------|-----------------|  
|[CJumpList::CJumpList](#cjumplist)|构造 `CJumpList` 对象。|  
|[CJumpList:: ~ CJumpList](#cjumplist__~cjumplist)|销毁 `CJumpList` 对象。|  
  
|名称|说明|  
|----------|-----------------|  
|[CJumpList::AbortList](#abortlist)|将列表生成事务中止且不提交。|  
|[CJumpList::AddDestination](#adddestination)|已重载。 将目标添加到列表。|  
|[CJumpList::AddKnownCategory](#addknowncategory)|将已知的类别追加到列表。|  
|[CJumpList::AddTask](#addtask)|已重载。 将项添加到规范的任务类别。|  
|[CJumpList::AddTasks](#addtasks)|将项添加到规范的任务类别。|  
|[CJumpList::AddTaskSeparator](#addtaskseparator)|添加任务之间的分隔符。|  
|[CJumpList::ClearAll](#clearall)|删除所有任务和已添加到的当前实例的目标`CJumpList`到目前为止。|  
|[CJumpList::ClearAllDestinations](#clearalldestinations)|删除已添加到的当前实例的所有目标`CJumpList`到目前为止。|  
|[CJumpList::CommitList](#commitlist)|结束列表生成事务并将报告的列表提交到相关联的存储 （在此情况下的注册表。）|  
|[CJumpList::GetDestinationList](#getdestinationlist)|检索到目标列表的接口指针。|  
|[CJumpList::GetMaxSlots](#getmaxslots)|检索项，包括可以在调用应用程序的目标菜单中显示的类别标头的最大数目。|  
|[CJumpList::GetRemovedItems](#getremoveditems)|返回表示项的数组中删除目标。|  
|[CJumpList::InitializeList](#initializelist)|开始一项列表生成事务。|  
|[CJumpList::SetAppID](#setappid)|设置的列表中将生成的应用程序用户模型 ID。|  
  
## <a name="inheritance-hierarchy"></a>继承层次结构  
 [CJumpList](../../mfc/reference/cjumplist-class.md)  
  
## <a name="requirements"></a>要求  
 **标头︰** afxadv.h  
  
##  <a name="_dtorcjumplist"></a>CJumpList:: ~ CJumpList  
 销毁 `CJumpList` 对象。  
  
```  
~CJumpList();
```  
  
##  <a name="abortlist"></a>CJumpList::AbortList  
 将列表生成事务中止且不提交。  
  
```  
void AbortList();
```  
  
### <a name="remarks"></a>备注  
 调用此方法不会有相同的效果销毁`CJumpList`而不调用`CommitList`。  
  
##  <a name="adddestination"></a>CJumpList::AddDestination  
 将目标添加到列表。  
  
```  
BOOL AddDestination(
    LPCTSTR lpcszCategoryName,  
    LPCTSTR strDestinationPath);

 
BOOL AddDestination(
    LPCTSTR strCategoryName,  
    IShellItem* pShellItem);

 
BOOL AddDestination(
    LPCTSTR strCategoryName,  
    IShellLink* pShellLink);
```  
  
### <a name="parameters"></a>参数  
 `lpcszCategoryName`  
 指定类别名称。 如果指定的类别不存在，将创建它。  
  
 `strDestinationPath`  
 指定目标文件的路径。  
  
 `strCategoryName`  
 指定类别名称。 如果指定的类别不存在，将创建它。  
  
 `pShellItem`  
 指定表示要添加的目标的命令行程序项目。  
  
 `pShellLink`  
 指定表示要添加的目标的命令行程序链接。  
  
### <a name="return-value"></a>返回值  
  
### <a name="remarks"></a>备注  
 实例`CJumpList`内部累计添加的目标，然后将它们在提交`CommitList`。  
  
##  <a name="addknowncategory"></a>CJumpList::AddKnownCategory  
 将已知的类别追加到列表。  
  
```  
BOOL AddKnownCategory(KNOWNDESTCATEGORY category);
```  
  
### <a name="parameters"></a>参数  
 `category`  
 指定一个已知的类别类型。 可以是`KDC_RECENT`，或`KDC_KNOWN`。  
  
### <a name="return-value"></a>返回值  
  
### <a name="remarks"></a>备注  
 已知的类别是我们将自动计算每个应用程序利用常用和最近类别`SHAddToRecentDocs`（或间接地使用它，如外壳中将其应用程序的代表自己调用在某些情况下）。  
  
##  <a name="addtask"></a>CJumpList::AddTask  
 将项添加到规范的任务类别。  
  
```  
BOOL AddTask(
    LPCTSTR strTargetExecutablePath,  
    LPCTSTR strCommandLineArgs,  
    LPCTSTR strTitle,  
    LPCTSTR strIconLocation,  
    int iIconIndex);  
  
BOOL AddTask(IShellLink* pShellLink);
```  
  
### <a name="parameters"></a>参数  
 `strTargetExecutablePath`  
 指定目标任务路径。  
  
 `strCommandLineArgs`  
 指定由 strTargetExecutablePath 指定的可执行文件的命令行参数。  
  
 `strTitle`  
 将显示在目标列表中的任务名称。  
  
 `strIconLocation`  
 将显示在目标列表以及标题中的图标的位置。  
  
 `iIconIndex`  
 图标索引。  
  
 `pShellLink`  
 表示要添加的任务的命令行程序链接。  
  
### <a name="return-value"></a>返回值  
  
### <a name="remarks"></a>备注  
 实例`CJumpList`累积指定的任务并将它们添加到在目标列表`CommitList`。 任务项将出现在应用程序的目标菜单底部类别。 在 UI 中填充时，此类别优先于所有其他类别。  
  
##  <a name="addtasks"></a>CJumpList::AddTasks  
 将项添加到规范的任务类别。  
  
```  
BOOL AddTasks(IObjectArray* pObjectCollection);
```  
  
### <a name="parameters"></a>参数  
 `pObjectCollection`  
 要添加的任务的集合。  
  
### <a name="return-value"></a>返回值  
  
### <a name="remarks"></a>备注  
 CJumpList 实例累积指定的任务，并将它们添加到在目标列表`CommitList`。 任务项将出现在应用程序的目标菜单底部类别。 在 UI 中填充时，此类别优先于所有其他类别。  
  
##  <a name="addtaskseparator"></a>CJumpList::AddTaskSeparator  
 添加任务之间的分隔符。  
  
```  
BOOL AddTaskSeparator();
```  
  
### <a name="return-value"></a>返回值  
 如果成功，则为非 0; 如果不是。  
  
##  <a name="cjumplist"></a>CJumpList::CJumpList  
 构造 `CJumpList` 对象。  
  
```  
CJumpList(BOOL bAutoCommit = TRUE);
```  
  
### <a name="parameters"></a>参数  
 `bAutoCommit`  
 如果此参数为 FALSE 列表不会自动在析构函数中提交。  
  
##  <a name="clearall"></a>CJumpList::ClearAll  
 删除所有任务和已添加到的当前实例的目标`CJumpList`到目前为止。  
  
```  
void ClearAll();
```  
  
### <a name="remarks"></a>备注  
 此方法清除并释放所有数据和内部接口。  
  
##  <a name="clearalldestinations"></a>CJumpList::ClearAllDestinations  
 删除已添加到 CJumpList 的当前实例到目前为止的所有目标。  
  
```  
void ClearAllDestinations();
```  
  
### <a name="remarks"></a>备注  
 如果您需要删除所有目的地，目标列表构建与当前会话中到目前为止添加，并且再次添加其他目标，则调用此函数。 如果内部`ICustomDestinationList`已初始化，它仍将保持活动状态。  
  
##  <a name="commitlist"></a>CJumpList::CommitList  
 结束列表生成事务，并提交到相关联的存储 （在此情况下注册表） 的报告的列表。  
  
```  
BOOL CommitList();
```  
  
### <a name="return-value"></a>返回值  
  
### <a name="remarks"></a>备注  
 提交是原子的。 如果提交失败，则将返回错误。  当`CommitList`调用时，当前将会清除已删除的项的列表。 调用此方法会重置该对象，以便它不具有活动的列表中构建事务。 若要更新此列表，`BeginList`需要再次调用。  
  
##  <a name="getdestinationlist"></a>CJumpList::GetDestinationList  
 检索到目标列表的接口指针。  
  
```  
ICustomDestinationList* GetDestinationList();
```  
  
### <a name="return-value"></a>返回值  
  
### <a name="remarks"></a>备注  
 如果跳转列表未初始化，或已提交或中止，则返回的值将`NULL`。  
  
##  <a name="getmaxslots"></a>CJumpList::GetMaxSlots  
 检索项，包括可以在调用应用程序的目标菜单中显示的类别标头的最大数目。  
  
```  
UINT GetMaxSlots() const;  
```  
  
### <a name="return-value"></a>返回值  
  
### <a name="remarks"></a>备注  
 应用程序可能会只报告大量的项和类别标题合并到此值。 如果调用`AppendCategory`， `AppendKnownCategory`，或`AddUserTasks`超过此数字，它们将返回失败。  
  
##  <a name="getremoveditems"></a>CJumpList::GetRemovedItems  
 返回表示项的数组中删除目标。  
  
```  
IObjectArray* GetRemovedItems();
```  
  
### <a name="return-value"></a>返回值  
  
### <a name="remarks"></a>备注  
 在跳转列表初始化过程中检索已删除的目标。 在生成新的目标列表时，应用程序应首先处理删除的目标列表中，清除已删除的列表枚举器返回任何项其跟踪数据。 如果应用程序尝试提供只在向调用当前事务中移除的项`BeginList`启动，重新添加该项目的方法调用将失败，以确保应用程序尊重已删除的列表。  
  
##  <a name="initializelist"></a>CJumpList::InitializeList  
 开始一项列表生成事务。  
  
```  
BOOL InitializeList();
```  
  
### <a name="return-value"></a>返回值  
  
### <a name="remarks"></a>备注  
 您不必显式调用此方法，除非你想要检索一个指向`ICustomDestinationList`使用`GetDestinationList`，使用的可用插槽数`GetMaxSlots`，或使用已删除项的列表`GetRemovedItems`。  
  
##  <a name="setappid"></a>CJumpList::SetAppID  
 设置的列表中将生成的应用程序用户模型 ID。  
  
```  
void SetAppID(LPCTSTR strAppID);
```  
  
### <a name="parameters"></a>参数  
 `strAppID`  
 一个字符串，指定应用程序用户模型 id。  
  
## <a name="see-also"></a>另请参阅  
 [类](../../mfc/reference/mfc-classes.md)
