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
ms.openlocfilehash: e7ec4f69b4bba497446c94afb94cb5a1d648f7c7
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80209565"
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

İşlem desteği sağlayıcıya özeldir. Kullanmakta olduğunuz sağlayıcı işlemleri destekliyorsa, `ITransaction` ve `ITransactionLocal` destekleyen bir oturum nesnesi (iç içe olmayan) bir işlem girebilir. OLE DB Şablon sınıfı [CSession](../../data/oledb/csession-class.md) bu arabirimleri destekler ve Visual C++'te işlem desteğinin uygulanması için önerilen yoldur.

## <a name="starting-and-ending-the-transaction"></a>Işlem başlatılıyor ve bitiriliyor

`StartTransaction`, `Commit`ve `Abort` yöntemlerini tüketicideki satır kümesi nesnesinde çağırabilirsiniz.

`ITransactionLocal::StartTransaction` çağrısı yeni bir yerel işlem başlatır. İşlemi başlattığınızda, işlemi yapana kadar sonraki işlemler tarafından uygulanan tüm değişiklikler veri deposuna uygulanmaz.

`ITransaction::Commit` veya `ITransaction::Abort` çağırmak işlemi sonlandırır. `Commit`, işlem kapsamındaki tüm değişikliklerin veri deposuna uygulanmasına neden olur. `Abort` işlem kapsamındaki tüm değişikliklerin iptal edilmesine neden olur ve veri deposu işlem başlatılmadan önceki durumda kalır.

## <a name="nested-transactions"></a>İç içe geçmiş Işlemler

[İç içe geçmiş bir işlem](/previous-versions/windows/desktop/ms716985(v=vs.85)) , oturumda zaten etkin bir işlem varken yeni bir yerel işlem başlattığınızda oluşur. Yeni işlem, geçerli işlemin altında iç içe geçmiş bir işlem olarak başlatılır. Sağlayıcı iç içe geçmiş işlemleri desteklemiyorsa, oturumda zaten etkin bir işlem olduğunda `StartTransaction` çağırmak XACT_E_XTIONEXISTS döndürür.

## <a name="distributed-transactions"></a>Dağıtılmış İşlemler

Dağıtılmış işlem, dağıtılmış verileri güncelleştiren bir işlemdir; diğer bir deyişle, birden fazla ağ bağlantılı bilgisayar sistemindeki veriler. Dağıtılmış bir sistem üzerinden işlemleri desteklemek istiyorsanız, OLE DB işlem desteği yerine .NET Framework kullanmanız gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[Erişimcileri Kullanma](../../data/oledb/using-accessors.md)
