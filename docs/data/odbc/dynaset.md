---
title: Dynaset
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC recordsets, dynasets
- ODBC cursor library [ODBC], dynasets
- keyset-driven cursors in dynasets
- cursors [ODBC], keyset-driven cursors in dynasets
- cursor library [ODBC], dynaset availability
- recordsets [C++], dynasets
- dynasets
ms.assetid: 2867e6be-208e-4fe7-8bbe-b8697cb1045c
ms.openlocfilehash: 66db216b92132638f04627ccf341e2e4ce20e429
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50585698"
---
# <a name="dynaset"></a>Dynaset

Bu konuda dinamik kümeler ve anlatılmaktadır kendi [kullanılabilirlik](#_core_availability_of_dynasets).

> [!NOTE]
>  Bu konu MFC ODBC sınıfları da dahil olmak üzere, geçerlidir [CRecordset](../../mfc/reference/crecordset-class.md). DAO sınıflardaki hakkında daha fazla bilgi için bkz. [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md). DAO ile dinamik türü kayıt kümeleri açabilirsiniz.

Bir dinamik kayıt ile dinamik özellikler kümesidir. Yaşam süresi boyunca dynaset modunda (genellikle bir dinamik olarak da adlandırılır) bir kayıt kümesi nesnesi aşağıdaki şekilde veri kaynağı ile eşitlenmiş durumda kalır. Çok kullanıcılı bir ortamda, diğer kullanıcılar veya kümenize kayıtları düzenleyemeyeceğiniz veya kayıt kümenize gösteren tabloya ekleyin. Uygulamanızı ekler veya kayıt kümesinden siler kayıt kümenize yansıtılır. Tabloya diğer kullanıcı ekleme kayıtları yansıtılmaz kümenize çağırarak dinamik yeniden kadar kendi `Requery` üye işlevi. Diğer kullanıcıların kayıt sildiğinizde, silme işlemlerini kümenizde MFC kodu atlar. Etkilenen kayda kaydırma hemen sonra var olan kayıtların düzenleme değişiklikleri diğer kullanıcıların kümenize yansıtılır.

Benzer şekilde, dinamik küme kayıtları yaptığınız düzenlemeleri dynaset'ler kullanımda diğer kullanıcılar tarafından yansıtılır. Bunlar kendi dynaset'ler requery kadar kayıtları eklediğiniz diğer kullanıcıların dynaset'ler içinde yansıtılmaz. Kayıt silme, "diğer kullanıcıların kayıt kümeleri içinde silinen"olarak işaretlenir. Aynı veritabanının birden çok bağlantı varsa (birden çok `CDatabase` nesneleri), bu bağlantıları ile ilişkili kayıt kümelerinde, diğer kullanıcıların kayıt kümeleri aynı duruma sahip.

Dynaset'ler en değerli alındığında veri içinde bir hava yolu rezervasyon sistemini (örneğin olarak) dinamik olması gerekir.

> [!NOTE]
> ODBC imleç kitaplığı yüklenmesi gereken ve dynaset'ler kullanmak için dynaset'ler destekleyen ve veri kaynağı bir ODBC sürücüsü gerekir. Daha fazla bilgi için [, kullanılabilirlik Dynaset'ler](#_core_availability_of_dynasets).

Bir kayıt kümesi bir dinamik olduğunu belirtmek için geçirmek `CRecordset::dynaset` ilk parametresi olarak `Open` kayıt nesnenizin üye işlevi.

> [!NOTE]
> Güncelleştirilebilir dynaset'ler için ODBC sürücüsünün ya da konumlandırılmış update ifadeleriyle desteklemesi gerekir veya `::SQLSetPos` ODBC API işlevi. Her ikisi de desteklenir, MFC kullanıyorsa `::SQLSetPos` verimlilik için.

##  <a name="_core_availability_of_dynasets"></a> Dynaset'ler kullanılabilirliği

Aşağıdaki gereksinimler karşılanırsa dynaset'ler MFC veritabanı sınıflarını destekler:

- ODBC imleç kitaplığı DLL bu veri kaynağı için kullanımda olmamalıdır.

   İmleç Kitaplığı kullandıysanız, bazı işlevler dynaset desteği için gerekli olan temel alınan ODBC sürücüsünün maskeler. Dynaset'ler kullanmak istediğiniz (ve bu bölümün geri kalanında açıklanan dynasets için gereken işlevselliği ODBC sürücünüz sahip varsa), MFC oluşturduğunuzda, imleç kitaplığı yüklenmemesine neden olabilir bir `CDatabase` nesne. Daha fazla bilgi için [ODBC](../../data/odbc/odbc-basics.md) ve [OpenEx](../../mfc/reference/cdatabase-class.md#openex) veya [açık](../../mfc/reference/cdatabase-class.md#open) sınıfının üye işlevinde `CDatabase`.

   ODBC terminolojisinde, dinamik kümeler ve anlık görüntüleri için işaretçiler olarak adlandırılır. Bir İmleç konumuna kayıt izlemek için kullanılan bir mekanizmadır.

- Veri kaynağınız için ODBC sürücüsünden anahtar kümesi temelli imleçler desteklemesi gerekir.

   Anahtar kümesi temelli imleçler bir tablodan veri alma ve bir anahtar kümesini depolama yönetin. Anahtarlar, kullanıcının belirli bir kayda kaydırdığında tablosundan geçerli verileri almak için kullanılır. Sürücünüzün Bu destek sağlayıp sağlamadığını belirlemek için çağrı `::SQLGetInfo` ODBC API işlevini *çağırın* parametresi.

   Anahtar kümesi desteği olmadan bir dinamik açmaya çalışırsanız, size bir `CDBException` AFX_SQL_ERROR_DYNASET_NOT_SUPPORTED dönüş kodu ile değeri.

- Veri kaynağınız için ODBC sürücüsü, genişletilmiş getirilirken desteklemesi gerekir.

   Genişletilmiş yakalamanın yanı sıra geriye doğru kaydırın, SQL sorgunuzun elde edilen kayıtları iletmek için yeteneğidir. Sürücünüzün bu yeteneği destekleyip desteklemediğini belirlemek için çağrı `::SQLGetFunctions` ODBC API işlevini *çağırın* parametresi.

Güncelleştirilebilir dynaset'ler (veya anlık görüntüleri, sorgunuzun) istiyorsanız, ODBC sürücüsünün de ya da desteklemelidir `::SQLSetPos` ODBC API işlevini veya konumlandırılmış güncelleştirmeler. `::SQLSetPos` İşlevi SQL deyimleri göndermeden veri kaynağını güncelleştirmek MFC sağlar. Bu destek varsa, MFC SQL kullanarak güncelleştirmeleri yapmak yerine kullanır. Sürücünüzün destekleyip desteklemediğini belirlemek için `::SQLSetPos`, çağrı `::SQLGetInfo` ile *öğesini* parametresi.

Konumlandırılmış güncelleştirmeler SQL söz dizimini kullanın (form **WHERE CURRENT OF** \<imleçadı >) veri kaynağında tablodaki belirli bir satırı tanımlamak için. Sürücünüzün konumlandırılmış güncelleştirmeler destekleyip desteklemediğini belirlemek için çağrı `::SQLGetInfo` ile *SQL_POSITIONED_STATEMENTS* parametresi.

Genellikle, MFC dynaset'ler (ancak değil salt iletme kayıt kümeleri) bir düzey 2 API uygunluğu ODBC sürücüsüyle gerektirir. Veri kaynağınız için bir sürücü için düzey 1 API kümesi uyuyorsa, hem güncelleştirilebilir ve salt okunur anlık görüntüler ve salt iletme kayıt kümeleri, ancak dinamik kümeleri kullanmaya devam edebilirsiniz. Ancak, düzey 1 sürücü genişletilmiş getirme destekleyip desteklemediğini dinamik kümeler ve anahtar kümesi temelli imleçler destekleyebilir. ODBC Uyumluluk düzeyleri hakkında daha fazla bilgi için bkz: [ODBC](../../data/odbc/odbc-basics.md).

> [!NOTE]
> Anlık görüntüleri hem dynaset'ler kullanmak isterseniz, bunları iki farklı temel gerekir `CDatabase` nesneleri (iki farklı bağlantı).

İçin kaydırma hemen sonra ODBC imleç kitaplığı tarafından tutulan Ara depolama kullanan anlık görüntüler bir kaydı dynaset'ler doğrudan veri kaynağından getirin. Bu veri kaynağı ile eşitlenmiş dinamik başlangıçta seçtiği kayıtları tutar.

Visual C++'ın bu sürümünde bulunan ODBC sürücülerinin listesini ve ek sürücüler hakkında bilgi için bkz: [ODBC sürücü listesi](../../data/odbc/odbc-driver-list.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Açık Veritabanı Bağlantısı (ODBC)](../../data/odbc/open-database-connectivity-odbc.md)