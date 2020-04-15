---
title: private (C++)
ms.date: 11/04/2016
f1_keywords:
- private_cpp
helpviewer_keywords:
- private keyword [C++]
ms.assetid: 94e99983-46a5-4e21-800c-28f8a7c6a8ff
ms.openlocfilehash: d6dc1ca309c096a4f5e857ade3d7550749991f3f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366213"
---
# <a name="private-c"></a>private (C++)

## <a name="syntax"></a>Sözdizimi

```
private:
   [member-list]
private base-class
```

## <a name="remarks"></a>Açıklamalar

Sınıf üyelerinin bir listesinden önce, **özel** anahtar kelime bu üyelerin yalnızca üye işlevlerden ve sınıfın arkadaşlarından erişilebilen bir anahtar kelime olduğunu belirtir. Bu, bir sonraki erişim belirticisine veya sınıfın sonuna kadar bildirilen tüm üyeler için geçerlidir.

Bir taban sınıfın adından önce, **özel** anahtar kelime, taban sınıfın ortak ve korumalı üyelerinin türemiş sınıfın özel üyeleri olduğunu belirtir.

Bir sınıftaki üyelerin varsayılan erişimi özeldir. Bir yapıveya birleşimdeki üyelerin varsayılan erişimi herkese açıktır.

Taban sınıfın varsayılan erişimi sınıflar için özel, yapılar için ortaktır. Sendikaların temel sınıfları olamaz.

İlgili bilgiler için, [sınıf üyelerine erişimi denetlemede](member-access-control-cpp.md) [arkadaş,](../cpp/friend-cpp.md) [ortak,](../cpp/public-cpp.md) [korumalı](../cpp/protected-cpp.md)ve üye erişim tablosuna bakın.

## <a name="clr-specific"></a>/clr Özel

CLR türlerinde, C++ erişim belirtici anahtar kelimeler **(genel,** **özel**ve **korumalı)** derlemelerle ilgili türlerin ve yöntemlerin görünürlüğünü etkileyebilir. Daha fazla bilgi için [Üye Erişim Denetimi'ne](member-access-control-cpp.md)bakın.

> [!NOTE]
> [/LN](../build/reference/ln-create-msil-module.md) ile derlenen dosyalar bu davranışdan etkilenmez. Bu durumda, tüm yönetilen sınıflar (ortak veya özel) görünür.

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

[Sınıf Üyelerine Erişimi Denetleme](member-access-control-cpp.md)<br/>
[Anahtar sözcükler](../cpp/keywords-cpp.md)
