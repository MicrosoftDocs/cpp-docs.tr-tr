---
title: "Sağlayıcınızda Serbest iş parçacığı oluşturmayı destekleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, multithreaded
- threading [C++], providers
ms.assetid: a91270dc-cdf9-4855-88e7-88a54be7cbe8
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 5cd5ce6b852b490334cbc8d49c6e967efffb3a6e
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="supporting-free-threading-in-your-provider"></a>Sağlayıcınızda Serbest İş Parçacığı Oluşturmayı Destekleme
İş parçacığı tüm OLE DB sağlayıcısı sınıfları ve kayıt defteri girdileri buna göre ayarlanır. Çok kullanıcılı durumlarda performansı yüksek düzeyde sağlanmasına yardımcı olmak amacıyla boş iş parçacığı desteklemek için iyi bir fikirdir. Sağlayıcınız iş parçacığı açısından güvenli tutmaya yardımcı olmak için kodunuzu düzgün bir şekilde engellendiğini doğrulamanız gerekir. Her yazma veya verileri depolamak kritik bölümler ile erişimini engellemelidir.  
  
 Her OLE DB sağlayıcı şablonu nesnesi kritik kendi bölümü vardır. Engellemeyi kolaylaştırmak için oluşturduğunuz her bir yeni sınıfın üst sınıfın alıp bir şablon sınıf olmalıdır bağımsız değişken olarak adı.  
  
 Aşağıdaki örnek, kodunuzu engelleme gösterilmektedir:  
  
```  
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
  
 Kritik bölümler ile koruma hakkında daha fazla bilgi için `Lock` ve `Unlock`, bkz: [çoklu iş parçacığı kullanımı: eşitleme sınıflarını kullanma](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).  
  
 Herhangi bir yöntem, geçersiz kılma da doğrulamanız gerekir (gibi `Execute`) iş parçacığı güvenlidir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB Sağlayıcı Şablonlarıyla Çalışma](../../data/oledb/working-with-ole-db-provider-templates.md)