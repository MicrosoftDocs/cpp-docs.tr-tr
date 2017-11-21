---
title: "OLE DB'de işlemleri destekleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- OLE DB consumer templates [C++], transaction support
- transactions [C++], OLE DB support for
- nested transactions [C++]
- OLE DB [C++], transaction support
- databases [C++], transactions
- distributed transactions [C++]
ms.assetid: 3d72e583-ad38-42ff-8f11-e2166d60a5a7
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 9a7b1e937a7fa1ab33ff74d3c4e42856928320fc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="supporting-transactions-in-ole-db"></a>OLE DB'de İşlemleri Destekleme
A [işlem](../../data/transactions-mfc-data-access.md) grubu ya da toplu iş, bir veri kaynağı güncelleştirmelerini bir dizi böylece tüm başarılı ve aynı anda kaydedilmeden ya da (herhangi biri başarısız olursa) hiçbirinin tamamlanmadığı için bir yoldur ve tüm işlem geri alındı. Bu işlem veri kaynağında sonucun bütünlüğünü sağlar.  
  
 OLE DB işlemleri ile aşağıdaki üç yöntemi destekler:  
  
-   [ITransactionLocal::StartTransaction](https://msdn.microsoft.com/en-us/library/ms709786.aspx)  
  
-   [ITransaction::Commit](https://msdn.microsoft.com/en-us/library/ms713008.aspx)  
  
-   [Iİşlem::Durdur](https://msdn.microsoft.com/en-us/library/ms709833.aspx)  
  
## <a name="relationship-of-sessions-and-transactions"></a>Oturumlar ve işlemler arasındaki ilişki  
 Bir tek veri kaynağı nesnesi, her biri veya belirli bir zamanda bir işlem kapsamı dışındaki olabilir, bir veya daha fazla oturum nesneleri oluşturabilirsiniz.  
  
 Bir oturum bir işlem girdiğinizde değil, o oturumdaki veri deposunda yapılan tüm iş hemen her yöntem çağrısı kararlıdır. (Bu bazen için otomatik kayıt işlemleri modu veya örtük modu adlandırılır.)  
  
 Bir oturum bir işlem girdiğinde, o oturumdaki veri deposunda yapılan tüm iş bu işlem bir parçasıdır ve kaydedilmiş veya tek bir birim olarak iptal edildi. (Bu bazen el ile kaydetme modu olarak adlandırılır.)  
  
 İşlem desteği sağlayıcıya özeldir. Kullanmakta olduğunuz sağlayıcı işlemleri, destekleyen bir oturum nesnesi destekliyorsa **ITransaction** ve **ITransactionLocal** basit bir girebilirsiniz (diğer bir deyişle, iç içe olmayan) işlem. OLE DB Şablonları sınıfı [CSession](../../data/oledb/csession-class.md) bu arabirimleri destekler ve işlem desteği Visual c++'ta uygulamak için önerilen yoldur.  
  
## <a name="starting-and-ending-the-transaction"></a>Başlangıç ve bitiş işlem  
 Çağırmanız `StartTransaction`, **yürütme**, ve **Abort** tüketicideki satır kümesi nesnesi yöntemleri.  
  
 Çağırma **ITransactionLocal::StartTransaction** yeni bir yerel işlem başlatır. İşlem başlattığınızda işlemi kaydedene kadar sonraki işlemleri tarafından zorunlu herhangi bir değişiklik gerçekte veri deposuna uygulanmaz.  
  
 Çağırma **ITransaction::Commit** veya **Iİşlem::Durdur** işlemi sonlandırır. **Commit** veri deposuna uygulanacak işlem kapsamı içinde tüm değişiklikleri neden olur. **Abort** kapsamında işlem iptal edilecek ve veri deposu olan tüm değişiklikleri değişmeden durumunda bunu neden olan işlem başlatmadan önce.  
  
## <a name="nested-transactions"></a>İç içe geçmiş işlemler  
 A [iç içe işlem](https://msdn.microsoft.com/en-us/library/ms716985.aspx) oturum zaten etkin bir işlem mevcut olduğunda yeni bir yerel işlem başlattığınızda ortaya çıkar. Yeni işlem geçerli işlemin altında iç içe geçmiş bir işlem olarak başlatılır. Sağlayıcı iç içe geçmiş işlemler desteklemiyorsa çağırma `StartTransaction` üzerinde olduğunda zaten etkin bir işlem oturum döndürür **XACT_E_XTIONEXISTS**.  
  
## <a name="distributed-transactions"></a>Dağıtılmış işlemler  
 Dağıtılmış işlem Dağıtılmış veri güncelleştiren bir işlemdir; diğer bir deyişle, verileri birden çok ağa bağlı bilgisayar sisteminde. Dağıtılmış bir sistemde işlemleri desteklemek istiyorsanız, OLE DB işlem desteği yerine .NET Framework kullanmanız gerekir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Erişimcileri kullanma](../../data/oledb/using-accessors.md)