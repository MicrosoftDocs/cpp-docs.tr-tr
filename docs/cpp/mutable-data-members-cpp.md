---
title: Değişebilir Veri Üyeleri (C++)
ms.date: 11/04/2016
f1_keywords:
- mutable_cpp
helpviewer_keywords:
- mutable keyword [C++]
ms.assetid: ebe89746-3d36-43a8-8d69-f426af23f551
ms.openlocfilehash: 8d592eb97f70bfc26c075317c57ec4d5c78e3956
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50514185"
---
# <a name="mutable-data-members-c"></a>Değişebilir Veri Üyeleri (C++)

Bu anahtar sözcüğü, yalnızca bir sınıfın statik olmayan ve sabit olmayan veri üyelerine uygulanabilir. Bir veri üyesi bildirilirse **değişebilir**, sonra da bu veri üyesi için bir değer atamak için yasal bir **const** üye işlevi.

## <a name="syntax"></a>Sözdizimi

```
mutable member-variable-declaration;
```

## <a name="remarks"></a>Açıklamalar

Örneğin, aşağıdaki kod hatasız çünkü derleyeceği `m_accessCount` olarak bildirilmiş **değişebilir**ve bu nedenle tarafından değiştirilebilir `GetFlag` olsa bile `GetFlag` const üye işlevi olmasıdır.

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

[Anahtar Sözcükler](../cpp/keywords-cpp.md)