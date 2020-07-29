---
title: private (C++)
ms.date: 11/04/2016
f1_keywords:
- private_cpp
helpviewer_keywords:
- private keyword [C++]
ms.assetid: 94e99983-46a5-4e21-800c-28f8a7c6a8ff
ms.openlocfilehash: 3b9df2ee2abcaca1c7c11c08ef73ae795a84310d
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87232254"
---
# <a name="private-c"></a>private (C++)

## <a name="syntax"></a>Sözdizimi

```
private:
   [member-list]
private base-class
```

## <a name="remarks"></a>Açıklamalar

Sınıf üyeleri listesinden önce, **`private`** anahtar sözcüğü, bu üyelerin yalnızca üye işlevlerden ve sınıfın arkadaşlarından erişilebilir olduğunu belirtir. Bu, bir sonraki erişim tanımlayıcısına veya sınıfın sonuna kadar belirtilen tüm Üyeler için geçerlidir.

Temel sınıfın adından önce, **`private`** anahtar sözcüğü, temel sınıfın ortak ve korunan üyelerinin türetilmiş sınıfın özel üyeleri olduğunu belirtir.

Bir sınıftaki üyelerin varsayılan erişimi özeldir. Bir yapıda veya birleşimde üyelerin varsayılan erişimi geneldir.

Temel sınıfa varsayılan erişim sınıflar için özeldir ve yapılar için geneldir. Birleşimler temel sınıflara sahip olamaz.

İlgili bilgiler için, [sınıf üyelerine erişimi denetleme](member-access-control-cpp.md)içindeki [arkadaş](../cpp/friend-cpp.md), [ortak](../cpp/public-cpp.md), [korumalı](../cpp/protected-cpp.md)ve üye erişim tablosuna bakın.

## <a name="clr-specific"></a>/clr Özel

CLR türlerinde, C++ erişim belirtici anahtar sözcükleri ( **`public`** , **`private`** ve **`protected`** ) derlemelerle ilgili olarak türlerin ve yöntemlerin görünürlüğünü etkileyebilir. Daha fazla bilgi için bkz. [üye Access Control](member-access-control-cpp.md).

> [!NOTE]
> [/Ln](../build/reference/ln-create-msil-module.md) ile derlenen dosyalar bu davranıştan etkilenmez. Bu durumda, tüm yönetilen sınıflar (ortak veya özel) görünür.

## <a name="end-clr-specific"></a>END /clr Özel

## <a name="example"></a>Örnek

```cpp
// keyword_private.cpp
class BaseClass {
public:
   // privMem accessible from member function
   int pubFunc() { return privMem; }
private:
   void privMem;
};

class DerivedClass : public BaseClass {
public:
   void usePrivate( int i )
      { privMem = i; }   // C2248: privMem not accessible
                         // from derived class
};

class DerivedClass2 : private BaseClass {
public:
   // pubFunc() accessible from derived class
   int usePublic() { return pubFunc(); }
};

int main() {
   BaseClass aBase;
   DerivedClass aDerived;
   DerivedClass2 aDerived2;
   aBase.privMem = 1;     // C2248: privMem not accessible
   aDerived.privMem = 1;  // C2248: privMem not accessible
                          //    in derived class
   aDerived2.pubFunc();   // C2247: pubFunc() is private in
                          //    derived class
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Sınıf üyelerine erişimi denetleme](member-access-control-cpp.md)<br/>
[Anahtar sözcükler](../cpp/keywords-cpp.md)
