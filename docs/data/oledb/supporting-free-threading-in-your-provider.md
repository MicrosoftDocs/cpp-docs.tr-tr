---
title: Sağlayıcınızda Serbest İş Parçacığı Oluşturmayı Destekleme
ms.date: 11/04/2016
helpviewer_keywords:
- OLE DB providers, multithreaded
- threading [C++], providers
ms.assetid: a91270dc-cdf9-4855-88e7-88a54be7cbe8
ms.openlocfilehash: 50e05b70a782dd343031443540790697e980c994
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80209564"
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

`Lock` ve `Unlock`ile önemli bölümleri koruma hakkında daha fazla bilgi için bkz. [Çoklu Iş parçacığı kullanımı: eşitleme sınıflarını kullanma](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).

Geçersiz kıldığınız tüm yöntemlerin (örneğin `Execute`) iş parçacığı açısından güvenli olduğunu doğrulayın.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB Sağlayıcı Şablonlarıyla Çalışma](../../data/oledb/working-with-ole-db-provider-templates.md)
