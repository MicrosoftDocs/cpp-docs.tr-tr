---
title: public (C++)
ms.date: 11/04/2016
f1_keywords:
- public_cpp
helpviewer_keywords:
- public keyword [C++]
ms.assetid: f3e10a59-39f6-4bcd-827e-3e99f8f89497
ms.openlocfilehash: bf8293c6a6cf12154b02979de08035807991052c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376046"
---
# <a name="public-c"></a>public (C++)

## <a name="syntax"></a>Sözdizimi

```
public:
   [member-list]
public base-class
```

## <a name="remarks"></a>Açıklamalar

Sınıf üyelerinin bir listesinden önce, **ortak** anahtar kelime bu üyelerin herhangi bir işlevden erişilebilir olduğunu belirtir. Bu, bir sonraki erişim belirticisine veya sınıfın sonuna kadar bildirilen tüm üyeler için geçerlidir.

Bir taban sınıfın adından önce, **ortak** anahtar kelime, taban sınıfın ortak ve korumalı üyelerinin, türetilmiş sınıfın sırasıyla ortak ve korumalı üyeleri olduğunu belirtir.

Bir sınıftaki üyelerin varsayılan erişimi özeldir. Bir yapıveya birleşimdeki üyelerin varsayılan erişimi herkese açıktır.

Taban sınıfın varsayılan erişimi sınıflar için özel, yapılar için ortaktır. Sendikaların temel sınıfları olamaz.

Daha fazla bilgi için, [Sınıf Üyelerine Erişimi Denetleme'de](member-access-control-cpp.md) [özel](../cpp/private-cpp.md), [korumalı,](../cpp/protected-cpp.md) [arkadaş](../cpp/friend-cpp.md)ve üye erişim tablosuna bakın.

## <a name="clr-specific"></a>/clr Özel

CLR türlerinde, C++ erişim belirtici anahtar kelimeler **(genel,** **özel**ve **korumalı)** derlemelerle ilgili türlerin ve yöntemlerin görünürlüğünü etkileyebilir. Daha fazla bilgi için [Üye Erişim Denetimi'ne](member-access-control-cpp.md)bakın.

> [!NOTE]
> [/LN](../build/reference/ln-create-msil-module.md) ile derlenen dosyalar bu davranışdan etkilenmez. Bu durumda, tüm yönetilen sınıflar (ortak veya özel) görünür.

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

[Sınıf Üyelerine Erişimi Denetleme](member-access-control-cpp.md)<br/>
[Anahtar sözcükler](../cpp/keywords-cpp.md)
