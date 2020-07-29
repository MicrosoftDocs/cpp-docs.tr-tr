---
title: allocate
ms.date: 11/04/2016
f1_keywords:
- allocate_cpp
helpviewer_keywords:
- __declspec keyword [C++], allocate
- allocate __declspec keyword
ms.assetid: 67828b31-de60-4c0e-b0a6-ef3aab22641d
ms.openlocfilehash: 0bf31423cd76c838cbeffa7458bbccb89592bf43
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87227627"
---
# <a name="allocate"></a>allocate

**Microsoft'a Özgü**

**`allocate`** Bildirim Belirleyicisi, veri öğesinin ayrılabileceği veri segmentini adlandırır.

## <a name="syntax"></a>Sözdizimi

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
