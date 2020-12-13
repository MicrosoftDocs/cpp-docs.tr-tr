---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4326'
title: Derleyici Uyarısı (düzey 1) C4326
ms.date: 08/27/2018
f1_keywords:
- C4326
helpviewer_keywords:
- C4326
ms.assetid: d44d2c4e-9456-42d3-b35b-4ba4b2d42ec7
ms.openlocfilehash: d7c82d7a0157b53e60281bbe7c45a38cc765a73d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340053"
---
# <a name="compiler-warning-level-1-c4326"></a>Derleyici Uyarısı (düzey 1) C4326

> '*Function*' dönüş türü '*type2*' yerine '*Type1*' olmalıdır

## <a name="remarks"></a>Açıklamalar

Bir işlev *Type1* dışında bir tür döndürdü. Örneğin, [/za](../../build/reference/za-ze-disable-language-extensions.md)kullanarak **Main** bir döndürmez **`int`** .

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
