---
description: 'Hakkında daha fazla bilgi edinin: OLE DB Işlemler destekleme'
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
ms.openlocfilehash: f8d01a0d359a3d33fbe4b88877d8a4452f257c16
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97272727"
---
# <a name="supporting-transactions-in-ole-db"></a>OLE DB'de İşlemleri Destekleme

Bir [işlem](../../data/transactions-mfc-data-access.md) , bir veri kaynağına yönelik bir dizi güncelleştirmeyi gruplamak veya toplu işlem için bir yoldur. böylece, tümü başarılı olur ve bir kez veya (bunlardan biri başarısız olursa) hiçbiri işlenir ve tüm işlem geri alınır. Bu işlem, veri kaynağındaki sonucun bütünlüğünü sağlar.

OLE DB, aşağıdaki üç yöntemle işlemleri destekler:

- [ITransactionLocal:: StartTransaction](/previous-versions/windows/desktop/ms709786(v=vs.85))

- [ITransaction:: COMMIT](/previous-versions/windows/desktop/ms713008(v=vs.85))

- [ITransaction:: Abort](/previous-versions/windows/desktop/ms709833(v=vs.85))

## <a name="relationship-of-sessions-and-transactions"></a>Oturumların ve Işlemlerin ilişkisi

Tek bir veri kaynağı nesnesi, her biri belirli bir zamanda bir işlemin kapsamı içinde veya dışında olabilen bir veya daha fazla oturum nesnesi oluşturabilir.

Bir oturum bir işlem girmezse, veri deposundaki bu oturum içinde yapılan tüm işler her yöntem çağrısında hemen işlenir. (Bu, bazen oto yürütme modu veya örtük mod olarak adlandırılır.)

Bir oturum bir işlem girdiğinde, veri deposundaki bu oturum içinde yapılan tüm işler bu işlemin bir parçasıdır ve tek bir birim olarak kaydedilir veya iptal edilir. (Bu, bazen el ile tamamlama modu olarak adlandırılır.)

İşlem desteği sağlayıcıya özeldir. Kullanmakta olduğunuz sağlayıcı işlemleri destekliyorsa, ve ' ı destekleyen bir oturum nesnesi `ITransaction` `ITransactionLocal` (iç içe olmayan) bir işlem girebilirler. OLE DB Şablon sınıfı [CSession](../../data/oledb/csession-class.md) bu arabirimleri destekler ve Visual C++ işlem desteğinin uygulanması için önerilen yoldur.

## <a name="starting-and-ending-the-transaction"></a>Işlem başlatılıyor ve bitiriliyor

`StartTransaction` `Commit` `Abort` Tüketicideki satır kümesi nesnesinde,, ve yöntemlerini çağırabilirsiniz.

Çağırma `ITransactionLocal::StartTransaction` Yeni bir yerel işlem başlatır. İşlemi başlattığınızda, işlemi yapana kadar sonraki işlemler tarafından uygulanan tüm değişiklikler veri deposuna uygulanmaz.

`ITransaction::Commit`İşlem çağrılıyor veya `ITransaction::Abort` sona eriyor. `Commit` işlem kapsamındaki tüm değişikliklerin veri deposuna uygulanmasına neden olur. `Abort` işlemin kapsamındaki tüm değişikliklerin iptal edilmesine ve veri deposunun işlem başlatılmadan önceki durumda bırakılmasına neden olur.

## <a name="nested-transactions"></a>İç içe geçmiş Işlemler

[İç içe geçmiş bir işlem](/previous-versions/windows/desktop/ms716985(v=vs.85)) , oturumda zaten etkin bir işlem varken yeni bir yerel işlem başlattığınızda oluşur. Yeni işlem, geçerli işlemin altında iç içe geçmiş bir işlem olarak başlatılır. Sağlayıcı iç içe geçmiş işlemleri desteklemiyorsa, `StartTransaction` oturum üzerinde zaten etkin bir işlem olduğunda ' ı çağırmak XACT_E_XTIONEXISTS döndürür.

## <a name="distributed-transactions"></a>Dağıtılmış İşlemler

Dağıtılmış işlem, dağıtılmış verileri güncelleştiren bir işlemdir; diğer bir deyişle, birden fazla ağ bağlantılı bilgisayar sistemindeki veriler. Dağıtılmış bir sistem üzerinden işlemleri desteklemek istiyorsanız, OLE DB işlem desteği yerine .NET Framework kullanmanız gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[Erişimcileri kullanma](../../data/oledb/using-accessors.md)
