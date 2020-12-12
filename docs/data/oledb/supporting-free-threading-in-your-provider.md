---
description: 'Hakkında daha fazla bilgi edinin: sağlayıcınızda ücretsiz Iş parçacığı destekleme'
title: Sağlayıcınızda Serbest İş Parçacığı Oluşturmayı Destekleme
ms.date: 11/04/2016
helpviewer_keywords:
- OLE DB providers, multithreaded
- threading [C++], providers
ms.assetid: a91270dc-cdf9-4855-88e7-88a54be7cbe8
ms.openlocfilehash: 4f6785dd85ae043ce0ee74c1dda4fa365c566729
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97286481"
---
# <a name="supporting-free-threading-in-your-provider"></a>Sağlayıcınızda Serbest İş Parçacığı Oluşturmayı Destekleme

Tüm OLE DB sağlayıcı sınıfları iş parçacığı açısından güvenlidir ve kayıt defteri girdileri buna göre ayarlanır. Çok kullanıcılı durumlarda yüksek düzeyde performans sağlamaya yardımcı olmak için ücretsiz iş parçacığı oluşturmayı desteklemek iyi bir fikirdir. Sağlayıcınızın iş parçacığını güvenli tutmaya yardımcı olmak için, kodunuzun düzgün şekilde engellendiğini doğrulamanız gerekir. Veri yazdığınızda veya depoladığınız zaman, kritik bölümlerle erişimi engellemeniz gerekir.

Her bir OLE DB sağlayıcısı şablonu nesnesinin kendi kritik bölümü vardır. Engellemeyi kolaylaştırmak için oluşturduğunuz her yeni sınıf, üst sınıf adını bağımsız değişken olarak alan bir şablon sınıfı olmalıdır.

Aşağıdaki örnek, kodunuzun nasıl engelleneceğini göstermektedir:

```cpp
template <class T>
class CMyObject<T> : public...

HRESULT MyObject::MyMethod(void)
{
   T* pT = (T*)this;      // this gets the parent class

// You don't need to do anything if you are only reading information

// If you want to write information, do the following:
   pT->Lock();         // engages critical section in the object
   ...;                // write whatever information you wish
   pT->Unlock();       // disengages the critical section
}
```

Ve ile kritik bölümleri koruma hakkında daha fazla bilgi için `Lock` `Unlock` bkz. [Çoklu iş parçacığı kullanımı: eşitleme sınıflarını kullanma](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).

Geçersiz kıldığınız tüm yöntemlerin (gibi `Execute` ) iş parçacığı açısından güvenli olduğunu doğrulayın.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB sağlayıcı şablonlarıyla çalışma](../../data/oledb/working-with-ole-db-provider-templates.md)
