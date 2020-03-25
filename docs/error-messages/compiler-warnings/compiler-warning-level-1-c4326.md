---
title: Derleyici Uyarısı (düzey 1) C4326
ms.date: 08/27/2018
f1_keywords:
- C4326
helpviewer_keywords:
- C4326
ms.assetid: d44d2c4e-9456-42d3-b35b-4ba4b2d42ec7
ms.openlocfilehash: 32bcd85b1cd1bb6c89678daae02f4f31a9318b6d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80162978"
---
# <a name="compiler-warning-level-1-c4326"></a>Derleyici Uyarısı (düzey 1) C4326

> '*Function*' dönüş türü '*type2*' yerine '*Type1*' olmalıdır

## <a name="remarks"></a>Açıklamalar

Bir işlev *Type1*dışında bir tür döndürdü. Örneğin, [/za](../../build/reference/za-ze-disable-language-extensions.md)kullanarak **Main** bir **int**döndürmedi.

## <a name="example"></a>Örnek

Aşağıdaki örnek C4326 oluşturur ve nasıl düzeltileceğini gösterir:

```cpp
// C4326.cpp
// compile with: /Za /W1
char main()
{
    // C4326, instead use int main()
}
```
