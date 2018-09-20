---
title: Yapıcı başlangıç düzeninde değişiklikler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- constructors, C++
ms.assetid: 8892c38d-6bf7-4cf7-ac8f-15e052135a79
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: fd54e9810131f3ddfabe458c70ddef081568a9cd
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46397695"
---
# <a name="changes-in-constructor-initialization-order"></a>Yapıcı Başlangıç Düzeninde Değişiklikler

Sınıf oluşturucuları için başlatma sırasını, C++ için Visual C++ için Yönetilen Uzantılar'dan değişti.

## <a name="comparison-of-constructor-initialization-order"></a>Oluşturucu başlatma sırası karşılaştırması

Yönetilen C++ için Uzantılar altında oluşturucusu başlatma aşağıdaki sırada bir hata oluştu:

1. Temel sınıfın Oluşturucusu varsa çağrılır.

1. Sınıf başlatma listesi değerlendirilir.

1. Sınıf oluşturucu kodu gövdesi yürütülür.

Bu yürütme sırası yerel C++ programlama olduğu gibi kuralların aynısını izler. Yeni Visual C++ dili aşağıdaki yürütme sırası CLR sınıflarını kullanır:

1. Sınıf başlatma listesi değerlendirilir.

1. Temel sınıfın Oluşturucusu varsa çağrılır.

1. Sınıf oluşturucu kodu gövdesi yürütülür.

Not; Bu değişiklik yalnızca CLR sınıflarını için geçerlidir. Visual C++ yerel sınıflarda yine de önceki kuralları takip edin. Her iki durumda da, bu kurallar, belirli bir sınıfın tüm hiyerarşiye zincirinde yukarı doğru basamaklı.

C++ için Yönetilen Uzantılar'ı kullanarak aşağıdaki kod örneği göz önünde bulundurun:

```
__gc class A
{
public:
   A() : _n(1)
   {
   }

protected:
   int _n;
};

__gc class B : public A
{
public:
   B() : _m(_n)
   {
   }
private:
   int _m;
};
```

Oluşturucu başlatma sırası Yukarıda açıklanmış, aşağıdaki yeni yürütme sırasını görmeliyiz sınıfının örneklerini `B` oluşturulur:

1. Temel sınıfın Oluşturucusu `A` çağrılır. `_n` Üyesi için başlatılan `1`.

1. Sınıfı için başlatma listesi `B` değerlendirilir. `_m` Üyesi için başlatılan `1`.

1. Kodu sınıfın gövdesi, `B` yürütülür.

Artık yeni Visual C++ sözdizimi aynı kodu göz önünde bulundurun:

```
ref class A
{
public:
   A() : _n(1)
   {
   }

protected:
   int _n;
};

ref class B : A
{
public:
   B() : _m(_n)
   {
   }
private:
   int _m;
};
```

Yeni bir yürütme sırası sınıfının örneklerini `B` altında yeni oluşturulan söz dizimi şu şekildedir:

1. Sınıfı için başlatma listesi `B` değerlendirilir. `_m` Üyesi için başlatılan `0` (`0` başlatılmamış değeri `_m` sınıf üyesi).

1. Temel sınıfın Oluşturucusu `A` çağrılır. `_n` Üyesi için başlatılan `1`.

1. Kodu sınıfın gövdesi, `B` yürütülür.

Benzer bir sözdizimi Bu kod örnekleri için farklı sonuçlar üreten unutmayın. Sınıfının oluşturucusu, `B` temel sınıftan bir değere bağlıdır `A` kendi üyesi başlatılamıyor. Ancak, sınıf için oluşturucu `A` değil henüz çağrılmış. Devralınan sınıf temel sınıfın oluşturucusunda gerçekleşmesi için bellek veya kaynak ayırma bağlı olduğunda bu tür bir bağımlılık özellikle tehlikeli olabilir.

## <a name="what-this-means-going-from-managed-extensions-for-c-to-visual-c-2010"></a>Yönetilen Uzantılar'dan C++ için Visual C++ 2010'a giderek Bunun anlamı

Çoğu durumda temel sınıflar devralınan sınıflar davranışını kavramı olmadığından sınıf oluşturucuları uygulanma sırası değişiklikleri programcıya saydam olmalıdır. Ancak, bu kod örnekte gösterildiği gibi temel sınıf üyelerinin değerlerini üzerinde başlatma listelerine bağlı olduğunda devralınan sınıflardaki oluşturucular büyük ölçüde etkilenebilir. Yönetilen Uzantılar'dan kodunuzu yeni sözdizimine C++ için getirdiğinizde Son gerçekleşmesi için yürütme burada garanti sınıf oluşturucu gövdesinde gibi yapıları taşıma göz önünde bulundurun.

## <a name="see-also"></a>Ayrıca Bkz.

[Yönetilen türler (C + +/ CL)](../dotnet/managed-types-cpp-cl.md)<br/>
[Oluşturucular](../cpp/constructors-cpp.md)
