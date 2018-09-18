---
title: ayırma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- allocate_cpp
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword [C++], allocate
- allocate __declspec keyword
ms.assetid: 67828b31-de60-4c0e-b0a6-ef3aab22641d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 25ebe45ebb85e13b6541057c57fd70da7361797f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46064853"
---
# <a name="allocate"></a>allocate

**Microsoft'a özgü**

**Tahsis** bildirim belirticisi içinde veri öğesi ayrılan bir veri segmentini adlandırır.

## <a name="syntax"></a>Sözdizimi

```
   __declspec(allocate("segname")) declarator
```

## <a name="remarks"></a>Açıklamalar

Adı *segname* aşağıdaki pragmalarından biri kullanılarak bildirilmelidir:

- [code_seg](../preprocessor/code-seg.md)

- [const_seg](../preprocessor/const-seg.md)

- [data_seg](../preprocessor/data-seg.md)

- [init_seg](../preprocessor/init-seg.md)

- [section](../preprocessor/section.md)

## <a name="example"></a>Örnek

```cpp
// allocate.cpp
#pragma section("mycode", read)
__declspec(allocate("mycode"))  int i = 0;

int main() {
}
```

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[__declspec](../cpp/declspec.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)