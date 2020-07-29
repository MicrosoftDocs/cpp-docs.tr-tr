---
title: Değişebilir Veri Üyeleri (C++)
ms.date: 11/04/2016
f1_keywords:
- mutable_cpp
helpviewer_keywords:
- mutable keyword [C++]
ms.assetid: ebe89746-3d36-43a8-8d69-f426af23f551
ms.openlocfilehash: 9370952f503850fbc296c3df912d4a0fafe163f0
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87227354"
---
# <a name="mutable-data-members-c"></a>Değişebilir Veri Üyeleri (C++)

Bu anahtar sözcük, yalnızca bir sınıfın statik olmayan ve const olmayan veri üyelerine uygulanabilir. Bir veri üyesi bildirilirse **`mutable`** , bu veri üyesine üye işlevden bir değer atama geçerli olur **`const`** .

## <a name="syntax"></a>Sözdizimi

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
