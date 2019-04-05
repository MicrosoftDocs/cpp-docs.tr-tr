---
title: Sağlayıcınızda Serbest İş Parçacığı Oluşturmayı Destekleme
ms.date: 11/04/2016
helpviewer_keywords:
- OLE DB providers, multithreaded
- threading [C++], providers
ms.assetid: a91270dc-cdf9-4855-88e7-88a54be7cbe8
ms.openlocfilehash: a2afb7354dd0447375ee6205b7c5d9a4755aa4b8
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59025344"
---
# <a name="supporting-free-threading-in-your-provider"></a>Sağlayıcınızda Serbest İş Parçacığı Oluşturmayı Destekleme

Tüm OLE DB sağlayıcısı sınıfları iş parçacığı bakımından güvenlidir ve kayıt defteri girdileri uygun şekilde ayarlanır. Yüksek düzeyde performans, çok kullanıcılı durumlarda sağlanmasına yardımcı olmak amacıyla ücretsiz iş parçacıklı desteklemek için iyi bir fikirdir. Sağlayıcınız iş parçacığı açısından güvenli olmasını sağlamak için kodunuzu düzgün bir şekilde engellendi doğrulamanız gerekir. Her yazma veya veri deposu kritik bölümler erişimle engellemeniz gerekir.

Her bir OLE DB sağlayıcı şablonu nesnesi kendi kritik bölümü vardır. Engellemeyi kolaylaştırmak için oluşturduğunuz her yeni sınıfı üst sınıfın alan bir şablon sınıfı olmalıdır bağımsız değişken olarak adı.

Aşağıdaki örnek, kodunuzu engellemek gösterilmektedir:

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

Kritik bölümler koruma hakkında daha fazla bilgi için `Lock` ve `Unlock`, bkz: [çoklu iş parçacığı kullanımı: Eşitleme sınıflarının nasıl kullanılacağını](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).

Doğrulama yöntemleri, geçersiz kılın (gibi `Execute`) iş parçacığı bakımından güvenlidir.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB Sağlayıcı Şablonlarıyla Çalışma](../../data/oledb/working-with-ole-db-provider-templates.md)