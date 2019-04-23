---
title: OLE DB'de İşlemleri Destekleme
ms.date: 10/24/2018
helpviewer_keywords:
- OLE DB consumer templates [C++], transaction support
- transactions [C++], OLE DB support for
- nested transactions [C++]
- OLE DB [C++], transaction support
- databases [C++], transactions
- distributed transactions [C++]
ms.assetid: 3d72e583-ad38-42ff-8f11-e2166d60a5a7
ms.openlocfilehash: 3c71200e39641a69443599e0445f89f469aceeda
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59038754"
---
# <a name="supporting-transactions-in-ole-db"></a>OLE DB'de İşlemleri Destekleme

A [işlem](../../data/transactions-mfc-data-access.md) grubu ya da toplu işlem, bir dizi veri kaynağına güncelleştirmeleri böylece tüm başarılı ve aynı anda taahhüt ya da (herhangi biri başarısız olursa) hiçbiri tamamlanmadığı için bir yoldur ve işlemin tümü geri alınır. Bu işlem veri kaynağında sonucun bütünlüğü sağlar.

OLE DB, aşağıdaki üç yöntemi ile işlemleri destekler:

- [ITransactionLocal::StartTransaction](/previous-versions/windows/desktop/ms709786(v=vs.85))

- [ITransaction::Commit](/previous-versions/windows/desktop/ms713008(v=vs.85))

- [Iİşlem::Durdur](/previous-versions/windows/desktop/ms709833(v=vs.85))

## <a name="relationship-of-sessions-and-transactions"></a>Oturumlar ve işlemler arasındaki ilişki

Bir tek veri kaynağı nesnesi, her biri içinde veya belirli bir zamanda bir işlem kapsamı dışında olabilir, bir veya daha fazla oturum nesneleri oluşturabilirsiniz.

Bir oturumu bir işlem girdiğinizde değil, ilgili oturum içindeki veri deposunda gerçekleştirilen tüm çalışma üzerinde her yöntem çağrısının hemen taahhüt eder. (Bu bazen otomatik yürütme modu veya örtük modu adlandırılır.)

Oturum, bir işlem girdiğinde, ilgili oturum içindeki veri deposunda gerçekleştirilen tüm çalışma bu işlem bir parçasıdır ve kaydedilmiş veya tek bir birim olarak durduruldu. (Bu bazen el ile tamamlama modu adlandırılır.)

İşlem, sağlayıcıya özgü desteğidir. Kullanmakta olduğunuz sağlayıcısı işlemleri destekleyen bir oturum nesnesi destekleyip desteklemediğini `ITransaction` ve `ITransactionLocal` (iç içe) bir işlem girebilirsiniz. OLE DB Şablonları sınıfı [CSession](../../data/oledb/csession-class.md) bu arabirimleri destekleyen ve Visual c++'ta işlem desteği uygulamak için önerilen yoldur.

## <a name="starting-and-ending-the-transaction"></a>Başlangıç ve bitiş işlem

Çağırmanızı `StartTransaction`, `Commit`, ve `Abort` satır kümesi nesnesi tüketicide yöntemleri.

Çağırma `ITransactionLocal::StartTransaction` yeni yerel bir işlem başlatır. İşlem başlattığınızda, sonraki işlemlerin tarafından uygulanan herhangi bir değişiklik işlemi yürütene kadar veri deposuna uygulanmaz.

Çağırma `ITransaction::Commit` veya `ITransaction::Abort` işlemi sonlandırır. `Commit` Veri deposuna uygulanması için işlem kapsamında tüm değişiklikleri neden olur. `Abort` işlem başlatmadan önce işlemin iptal edilmesine ve veri deposu kapsamındaki tüm değişiklikleri bırakılmış durumda bunu neden vardı.

## <a name="nested-transactions"></a>İç içe işlemler

A [işlem iç içe geçmiş](/previous-versions/windows/desktop/ms716985(v=vs.85)) oturum etkin bir işlem zaten mevcut olduğunda yeni bir yerel işlem başlatıldığında gerçekleşir. Yeni işlem geçerli işlemin altında iç içe geçmiş bir işlem olarak başlatıldı. İç içe işlem sağlayıcısı desteklemiyorsa, çağırma `StartTransaction` zaten oturum etkin bir işlem XACT_E_XTIONEXISTS döndürür.

## <a name="distributed-transactions"></a>Dağıtılmış İşlemler

Dağıtılmış işlem dağıtılmış verileri güncelleştiren bir işlemdir; diğer bir deyişle, veriler üzerinde birden fazla ağa bağlı bilgisayar sistemi. Dağıtılmış bir sistemde işlemleri desteklemek istiyorsanız, OLE DB transaction desteği yerine .NET Framework kullanmanız gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[Erişimcileri Kullanma](../../data/oledb/using-accessors.md)