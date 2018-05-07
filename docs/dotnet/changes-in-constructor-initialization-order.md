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
ms.openlocfilehash: 32dad73e3d2026726e3042b0c619eeff11a5f57c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="changes-in-constructor-initialization-order"></a>Yapıcı Başlangıç Düzeninde Değişiklikler
Sınıf oluşturucuları için başlatma sırasını Visual C++ için C++ için Yönetilen Uzantılar'dan değiştirdi.  
  
## <a name="comparison-of-constructor-initialization-order"></a>Oluşturucusu başlatma sırası karşılaştırması  
 Altında C++ için Yönetilen Uzantılar, aşağıdaki sırayla oluşturucusu başlatma hata oluştu:  
  
1.  Taban sınıf varsa çağrılır.  
  
2.  Sınıf başlatma listesi değerlendirilir.  
  
3.  Sınıf oluşturucu kod gövdesi yürütülür.  
  
 Bu yürütme sırası, yerel C++ programlama olduğu gibi aynı kuralları izler. Yeni Visual C++ dili CLR sınıflarını aşağıdaki yürütme sırası önerir:  
  
1.  Sınıf başlatma listesi değerlendirilir.  
  
2.  Taban sınıf varsa çağrılır.  
  
3.  Sınıf oluşturucu kod gövdesi yürütülür.  
  
 Bu değişikliğin yalnızca CLR sınıfları için geçerlidir unutmayın; Visual C++ yerel sınıflarda hala önceki kuralları izleyin. Her iki durumda da, bu kurallar, belirli bir sınıfın tüm hiyerarşinin zincirinde yukarı basamaklı.  
  
 C++ için Yönetilen Uzantılar kullanarak aşağıdaki kod örneği göz önünde bulundurun:  
  
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
  
 Oluşturucusu başlatma sırası Yukarıda açıklanmış, aşağıdaki yeni yürütme sırasını görmeliyiz sınıfının örnekleri `B` oluşturulur:  
  
1.  Taban sınıf `A` çağrılır. `_n` Üye başlatılır `1`.  
  
2.  Sınıfı için başlatma listesi `B` değerlendirilir. `_m` Üye başlatılır `1`.  
  
3.  Kodu sınıfın gövdesi, `B` yürütülür.  
  
 Şimdi yeni Visual C++ sözdiziminde aynı kodu göz önünde bulundurun:  
  
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
  
 Yeni yürütme sırasını sınıfının örnekleri `B` yeni altında oluşturulan sözdizimi aşağıdaki gibidir:  
  
1.  Sınıfı için başlatma listesi `B` değerlendirilir. `_m` Üye başlatılır `0` (`0` başlatılmamış değeri `_m` sınıf üyesi).  
  
2.  Taban sınıf `A` çağrılır. `_n` Üye başlatılır `1`.  
  
3.  Kodu sınıfın gövdesi, `B` yürütülür.  
  
 Benzer bir sözdizimi Bu kod örnekleri için farklı sonuçlar üretir unutmayın. Sınıf `B` temel sınıf arasında bir değer bağlıdır `A` kendi üyesi başlatılamadı. Ancak, sınıf oluşturucusu `A` değil henüz çağrılmış durumda. Devralınan sınıf bir taban sınıf oluşturucu gerçekleşmesi için bir bellek veya kaynak ayırma bağlı olduğunda bu tür bir bağımlılık özellikle tehlikeli olabilir.  
  
## <a name="what-this-means-going-from-managed-extensions-for-c-to-visual-c-2010"></a>Visual C++ 2010 C++ için Yönetilen Uzantılar'dan giderek Bunun anlamı  
 Temel sınıflar devralınan sınıfların davranış kavramı olduğundan çoğu durumda sınıf oluşturucular yürütme sırasını değişiklikler için programcı saydam olmalıdır. Ancak, bu kod örnekleri gösterdiği gibi başlatma listelerine taban sınıfı üyeleri değerlerine bağlı olduğunda devralınan sınıfların oluşturucular büyük ölçüde etkilenebilir. Yönetilen Uzantılar'dan kodunuzu yeni sözdizimine C++ için taşıdığınızda Son gerçekleşmesi için yürütme burada garanti sınıfı oluşturucusu gövdesini böyle yapıları taşıma göz önünde bulundurun.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yönetilen türler (C + +/ CL)](../dotnet/managed-types-cpp-cl.md)   
 [Oluşturucular](../cpp/constructors-cpp.md)   
 