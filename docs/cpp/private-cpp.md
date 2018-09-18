---
title: Özel (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- private_cpp
dev_langs:
- C++
helpviewer_keywords:
- private keyword [C++]
ms.assetid: 94e99983-46a5-4e21-800c-28f8a7c6a8ff
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 20d064a1154126878ce75d9dd08d88fa9d65f83c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46028564"
---
# <a name="private-c"></a>private (C++)

## <a name="syntax"></a>Sözdizimi

```
private:
   [member-list]
private base-class
```

## <a name="remarks"></a>Açıklamalar

Sınıf üyeleri listesi önce geldiği zaman **özel** anahtar sözcüğü, bu üyeler yalnızca üye işlevleri ve arkadaş sınıfı erişilebilir olduğunu belirtir. Bu, sonraki erişim belirticisi veya sınıf sonuna kadar bildirilen tüm üyeleri için geçerlidir.

Bir temel sınıfın adından önce zaman **özel** anahtar sözcüğü, temel sınıfın genel ve korumalı üyeler türetilmiş sınıfın özel üyeleri olduğunu belirtir.

Bir sınıf içinde üyelerin varsayılan erişimi özeldir. Bir yapı veya birleşim üyelerin varsayılan erişimi geneldir.

Özel sınıfları ve yapıları için ortak bir taban sınıfın varsayılan erişim. Birleşimlerin temel sınıfları olamaz.

İlgili bilgiler için bkz. [arkadaş](../cpp/friend-cpp.md), [genel](../cpp/public-cpp.md), [korumalı](../cpp/protected-cpp.md)ve üye erişimi tablosu [sınıfüyelerineerişimidenetleme](member-access-control-cpp.md).

## <a name="clr-specific"></a>/clr Özel

CLR türlerinde, C++ erişim belirtici anahtar sözcükleri (**genel**, **özel**, ve **korumalı**) türler ve Derlemelerle yöntemlerin görünürlüğünü etkileyebilir. Daha fazla bilgi için [üye erişim denetimi](member-access-control-cpp.md).

> [!NOTE]
>  İle derlenmiş dosyalar [/LN](../build/reference/ln-create-msil-module.md) Bu davranıştan etkilenmez. Bu durumda, tüm yönetilen sınıflar (ortak veya özel) görünür.

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
[Anahtar Sözcükler](../cpp/keywords-cpp.md)