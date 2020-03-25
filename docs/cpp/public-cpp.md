---
title: public (C++)
ms.date: 11/04/2016
f1_keywords:
- public_cpp
helpviewer_keywords:
- public keyword [C++]
ms.assetid: f3e10a59-39f6-4bcd-827e-3e99f8f89497
ms.openlocfilehash: dd45430543ead7258096be8f3d8cef0141f27b4e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80179198"
---
# <a name="public-c"></a>public (C++)

## <a name="syntax"></a>Sözdizimi

```
public:
   [member-list]
public base-class
```

## <a name="remarks"></a>Açıklamalar

Sınıf üyeleri listesinden önce, **Public** anahtar sözcüğü, bu üyelerin herhangi bir işlevden erişilebilir olduğunu belirtir. Bu, bir sonraki erişim tanımlayıcısına veya sınıfın sonuna kadar belirtilen tüm Üyeler için geçerlidir.

Bir temel sınıfın adından önce, **Public** anahtar sözcüğü, temel sınıfın ortak ve korunan üyelerinin, türetilmiş sınıfın sırasıyla ortak ve korumalı Üyeler olduğunu belirtir.

Bir sınıftaki üyelerin varsayılan erişimi özeldir. Bir yapıda veya birleşimde üyelerin varsayılan erişimi geneldir.

Temel sınıfa varsayılan erişim sınıflar için özeldir ve yapılar için geneldir. Birleşimler temel sınıflara sahip olamaz.

Daha fazla bilgi için bkz. [sınıf üyelerine erişimi denetleme](member-access-control-cpp.md)içindeki [özel](../cpp/private-cpp.md), [korunan](../cpp/protected-cpp.md), [arkadaş](../cpp/friend-cpp.md)ve üye erişim tablosu.

## <a name="clr-specific"></a>/clr Özel

C++ CLR türlerinde, erişim belirleyicisi anahtar sözcükleri (**genel**, **özel**ve **korumalı**) derlemelerle ilgili olarak türlerin ve yöntemlerin görünürlüğünü etkileyebilir. Daha fazla bilgi için bkz. [üye Access Control](member-access-control-cpp.md).

> [!NOTE]
>  [/Ln](../build/reference/ln-create-msil-module.md) ile derlenen dosyalar bu davranıştan etkilenmez. Bu durumda, tüm yönetilen sınıflar (ortak veya özel) görünür.

## <a name="end-clr-specific"></a>END /clr Özel

## <a name="example"></a>Örnek

```cpp
// keyword_public.cpp
class BaseClass {
public:
   int pubFunc() { return 0; }
};

class DerivedClass : public BaseClass {};

int main() {
   BaseClass aBase;
   DerivedClass aDerived;
   aBase.pubFunc();       // pubFunc() is accessible
                          //    from any function
   aDerived.pubFunc();    // pubFunc() is still public in
                          //    derived class
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Sınıf üyelerine erişimi denetleme](member-access-control-cpp.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)
