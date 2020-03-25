---
title: Değişebilir Veri Üyeleri (C++)
ms.date: 11/04/2016
f1_keywords:
- mutable_cpp
helpviewer_keywords:
- mutable keyword [C++]
ms.assetid: ebe89746-3d36-43a8-8d69-f426af23f551
ms.openlocfilehash: db3a9594a77a9ada971213eaea74a9842bd96a54
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80179347"
---
# <a name="mutable-data-members-c"></a>Değişebilir Veri Üyeleri (C++)

Bu anahtar sözcük, yalnızca bir sınıfın statik olmayan ve const olmayan veri üyelerine uygulanabilir. Bir veri üyesi **değişebilir**olarak bildirilirse, bu veri üyesine bir **const** üye işlevinden bir değer atama geçerli olur.

## <a name="syntax"></a>Sözdizimi

```
mutable member-variable-declaration;
```

## <a name="remarks"></a>Açıklamalar

Örneğin, `m_accessCount` **kesilebilir**olarak bildirildiği ve bu nedenle `GetFlag` bir const üye işlevi olsa da `GetFlag` tarafından değiştirilebilecek için aşağıdaki kod hatasız olarak derlenir.

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
