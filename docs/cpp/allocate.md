---
description: 'Daha fazla bilgi edinin: ayır'
title: allocate
ms.date: 11/04/2016
f1_keywords:
- allocate_cpp
helpviewer_keywords:
- __declspec keyword [C++], allocate
- allocate __declspec keyword
ms.assetid: 67828b31-de60-4c0e-b0a6-ef3aab22641d
ms.openlocfilehash: 0a30b113ca9271dc53777073ea0a80bac0f16bcb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97288288"
---
# <a name="allocate"></a>allocate

**Microsoft'a Özgü**

**`allocate`** Bildirim Belirleyicisi, veri öğesinin ayrılabileceği veri segmentini adlandırır.

## <a name="syntax"></a>Syntax

> **`__declspec(allocate("`***segname* **`))`** *bildirimci*

## <a name="remarks"></a>Açıklamalar

Aşağıdaki pragmaların biri kullanılarak, *segname* adı bildirilmelidir:

- [code_seg](../preprocessor/code-seg.md)

- [const_seg](../preprocessor/const-seg.md)

- [data_seg](../preprocessor/data-seg.md)

- [init_seg](../preprocessor/init-seg.md)

- [kısmı](../preprocessor/section.md)

## <a name="example"></a>Örnek

```cpp
// allocate.cpp
#pragma section("mycode", read)
__declspec(allocate("mycode"))  int i = 0;

int main() {
}
```

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[`__declspec`](../cpp/declspec.md)<br/>
[Anahtar sözcükler](../cpp/keywords-cpp.md)
