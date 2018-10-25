---
title: Sağlayıcınızda Serbest iş parçacığı oluşturmayı destekleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, multithreaded
- threading [C++], providers
ms.assetid: a91270dc-cdf9-4855-88e7-88a54be7cbe8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1235818474f734bf21afb51a6b4e8ed0a7b88f17
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50079921"
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

Kritik bölümler koruma hakkında daha fazla bilgi için `Lock` ve `Unlock`, bkz: [çoklu iş parçacığı kullanımı: eşitleme sınıflarını kullanma](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).

Herhangi bir yöntem, geçersiz kılma da doğrulamanız gerekir (gibi `Execute`) iş parçacığı bakımından güvenlidir.

## <a name="see-also"></a>Ayrıca Bkz.

[OLE DB Sağlayıcı Şablonlarıyla Çalışma](../../data/oledb/working-with-ole-db-provider-templates.md)