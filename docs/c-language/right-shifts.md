---
title: 右移
ms.date: 11/04/2016
ms.assetid: c878e97d-ea3c-4c6b-90a8-b1b24b2d5b19
ms.openlocfilehash: c34373f69a41ad65031753cd352098dce7e98ef4
ms.sourcegitcommit: f4be868c0d1d78e550fba105d4d3c993743a1f4b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/12/2019
ms.locfileid: "56149474"
---
# <a name="right-shifts"></a>右移

带符号的整型负值右移位的结果

将负值向右移位可生成绝对值的一半（向下舍入）。 例如，带符号 `short` 值 -253（十六进制 0xFF03，二进制 11111111 00000011）向右移一位会生成 -127（十六进制 0xFF81，二进制 11111111 10000001）。 正 253 向右移位生成 +126。

右移保留带符号的整数类型的符号位。 当带符号的整数向右移位时，最高有效位将保留。 例如，如果 0xF0000000 是带符号的 `int`，则右移位生成 0xF8000000。 将负数 `int` 右移位 32 次会生成 0xFFFFFFFF。

当无符号的整数右移位时，将清除最高有效位。 例如，如果 0xF000 是无符号的，则结果为 0x7800。 将 `unsigned` 或正数 `int` 右移位 32 次会生成 0x00000000。

## <a name="see-also"></a>请参阅

[整数](../c-language/integers.md)
