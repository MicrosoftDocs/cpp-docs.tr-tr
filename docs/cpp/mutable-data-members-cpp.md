---
description: 'Daha fazla bilgi edinin: değişebilir veri üyeleri (C++)'
title: Değişebilir Veri Üyeleri (C++)
ms.date: 11/04/2016
f1_keywords:
- mutable_cpp
helpviewer_keywords:
- mutable keyword [C++]
ms.assetid: ebe89746-3d36-43a8-8d69-f426af23f551
ms.openlocfilehash: a288b382b456fa313c49832bd2d13aaceb269be9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97313820"
---
# <a name="mutable-data-members-c"></a>Değişebilir Veri Üyeleri (C++)

Bu anahtar sözcük, yalnızca bir sınıfın statik olmayan ve const olmayan veri üyelerine uygulanabilir. Bir veri üyesi bildirilirse **`mutable`** , bu veri üyesine üye işlevden bir değer atama geçerli olur **`const`** .

## <a name="syntax"></a>Syntax

```
mutable member-variable-declaration;
```

## <a name="remarks"></a>Açıklamalar

Örneğin, aşağıdaki kod, olarak bildirildiği için hata olmadan derlenir `m_accessCount` **`mutable`** ve bu nedenle, `GetFlag` `GetFlag` bir const üye işlevi olsa da değiştirilebilir.

```cpp
// mutable.cpp
class X
{
public:
   bool GetFlag() const
   {
      m_accessCount++;
      return m_flag;
   }
private:
   bool m_flag;
   mutable int m_accessCount;
};

int main()
{
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Anahtar sözcükler](../cpp/keywords-cpp.md)
