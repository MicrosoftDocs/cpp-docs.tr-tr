---
description: 'Daha fazla bilgi edinin: Dynaset'
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
ms.openlocfilehash: 3c4a8edf1d0058045affc436bb8c9ee1c7e8bf4d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97239681"
---
# <a name="dynaset"></a>Dynaset

Bu konuda, dinamik kümeler açıklanmakta ve [kullanılabilirlikleri](#_core_availability_of_dynasets)anlatılmaktadır.

> [!NOTE]
> Bu konu, [CRecordset](../../mfc/reference/crecordset-class.md)dahil olmak üzere MFC ODBC sınıfları için geçerlidir. DAO sınıflarında dinamik kümeler hakkında daha fazla bilgi için bkz. [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md). DAO ile, değişken tür kayıt kümelerini açabilirsiniz.

DYNASET, dinamik özelliklere sahip bir kayıt kümesidir. Bağımsız değişken modundaki (genellikle Dynaset olarak adlandırılır) bir kayıt kümesi nesnesi, veri kaynağıyla aşağıdaki şekilde eşitlenmiş olarak kalır. Çok kullanıcılı bir ortamda, diğer kullanıcılar, dinamik kümenize ait kayıtları düzenleyebilir veya silebilir ya da Dynaset 'in gösterdiği tabloya kayıt ekleyebilirsiniz. Uygulamanızın kayıt kümesine eklediği veya kümeden sildiği kayıtlar, dinamik kümenize yansıtılır. Diğer kullanıcıların tabloya ekleyen kayıtlar, üye işlevini çağırarak Dynaset 'i yeniden oluşturulana kadar dinamik kümenize yansıtılmayacaktır `Requery` . Diğer kullanıcılar kayıtları sildiği zaman, MFC kodu kayıt kümenizde silmeleri atlar. Diğer kullanıcıların, var olan kayıtlarda değişiklik düzenlemesi, etkilenen kayda doğru kaydırdığınızda, dinamik kümenize yansıtılır.

Benzer şekilde, bir Dynaset içindeki kayıtlarda yaptığınız düzenlemeler, diğer kullanıcılar tarafından kullanılan dinamik kümeler halinde yansıtılır. Eklediğiniz kayıtlar, dinamik kümeleri yeniden sorgulanana kadar diğer kullanıcıların dinamik kümeleri ' ne yansıtılmaz. Sildiğiniz kayıtlar, diğer kullanıcıların kayıt kümelerinde "silindi" olarak işaretlenir. Aynı veritabanına (birden fazla nesne) birden çok bağlantınız varsa `CDatabase` , bu bağlantılarla ilişkili kayıt kümeleri, diğer kullanıcıların kayıt kümeleriyle aynı duruma sahiptir.

Veri kümeleri, bir hava yolu ayırma sisteminde (örneğin) verilerin dinamik olması gerektiğinde en değerlidir.

> [!NOTE]
> Dinamik kümeleri kullanmak için, veri kaynağınız için dinamik kümeleri destekleyen bir ODBC sürücünüz olmalıdır ve ODBC imleç kitaplığı yüklenmemelidir. Daha fazla bilgi için bkz. [Dinamik kümeler kullanılabilirliği](#_core_availability_of_dynasets).

Bir kayıt kümesinin bir Dynaset olduğunu belirtmek için, `CRecordset::dynaset` `Open` kayıt kümesi nesnenizin üye işlevine ilk parametre olarak geçirin.

> [!NOTE]
> Güncelleştirilebilir dinamik kümeler için, ODBC sürücünüzün konumlandırılmış Update deyimlerini veya `::SQLSetPos` ODBC API işlevini desteklemesi gerekir. Her ikisi de destekleniyorsa, MFC `::SQLSetPos` verimlilik için kullanır.

## <a name="availability-of-dynasets"></a><a name="_core_availability_of_dynasets"></a> Dinamik kümeler kullanılabilirliği

MFC veritabanı sınıfları, aşağıdaki gereksinimler karşılandığında dinamik kümeleri destekler:

- ODBC imleç kitaplığı DLL dosyası bu veri kaynağı için kullanımda olmamalıdır.

   İmleç kitaplığı kullanılıyorsa, küme kümesi desteği için gerekli olan temel ODBC sürücüsünün bazı işlevlerini maskeler. Dinamik kümeleri kullanmak istiyorsanız (ve ODBC sürücünüz, bu bölümün geri kalanında açıklandığı gibi, dinamik kümeler için gereken işlevlere sahipse), bir nesne oluştururken MFC 'nin imleç kitaplığını yükleyememesine neden olabilirsiniz `CDatabase` . Daha fazla bilgi için bkz. [ODBC](../../data/odbc/odbc-basics.md) ve sınıfın [OpenEx](../../mfc/reference/cdatabase-class.md#openex) veya [Open](../../mfc/reference/cdatabase-class.md#open) üye işlevi `CDatabase` .

   ODBC terminolojisinde, dinamik kümeler ve anlık görüntüler imleçler olarak adlandırılır. İmleç bir kayıt kümesindeki konumunu izlemek için kullanılan bir mekanizmadır.

- Veri kaynağınız için ODBC sürücüsü, anahtar kümesi temelli imleçleri desteklemelidir.

   Anahtar kümesi temelli imleçler bir anahtarlar kümesini alarak ve depolayarak bir tablodaki verileri yönetir. Anahtarlar, Kullanıcı belirli bir kayıt üzerinde kaydırıldığında tablodaki geçerli verileri almak için kullanılır. Sürücünüzün bu desteği sağladığını öğrenmek için, `::SQLGetInfo` *SQL_SCROLL_OPTIONS* parametresiyle ODBC API işlevini çağırın.

   Anahtar kümesi desteği olmadan bir Dynaset açmaya çalışırsanız, `CDBException` AFX_SQL_ERROR_DYNASET_NOT_SUPPORTED dönüş kodu değeri ile birlikte alırsınız.

- Veri kaynağınız için ODBC sürücüsünün genişletilmiş getirme desteği gerekir.

   Genişletilmiş getirme, geriye doğru kaymanın yanı sıra SQL sorgunuzun sonuç kayıtlarını ileriye doğru kaydırabilme olanağıdır. Sürücünüzün bu özelliği destekleyip desteklemediğini anlamak için, `::SQLGetFunctions` *SQL_API_SQLEXTENDEDFETCH* parametresiyle ODBC API işlevini çağırın.

Güncelleştirilebilir dinamik kümeleri (veya anlık görüntüleri bu şekilde) istiyorsanız, ODBC sürücünüzün `::SQLSetPos` ODBC API işlevini veya konumlandırılmış güncelleştirmeleri desteklemesi de gerekir. `::SQLSetPos`İşlevi, MFC 'nın SQL deyimleri göndermeden veri kaynağını güncelleştirmesine izin verir. Bu destek varsa, MFC SQL kullanarak güncelleştirme yapmak için bunu tercih altında kullanır. Sürücünüzün destekleyip desteklemediğini öğrenmek için `::SQLSetPos` `::SQLGetInfo` *SQL_POS_OPERATIONS* parametresiyle çağırın.

Konumlandırılmış güncelleştirmeler,  \<cursorname> veri kaynağındaki tablodaki belirli bir SATıRı tanımlamak için SQL söz dizimini (geçerli olduğu biçimde) kullanır. Sürücünüzün konumlandırılmış güncelleştirmeleri destekleyip desteklemediğini öğrenmek için `::SQLGetInfo` *SQL_POSITIONED_STATEMENTS* parametresiyle çağırın.

Genellikle MFC dinamik kümeleri (yalnızca iletme kayıt kümeleri), düzey 2 API uyumluluğu olan bir ODBC sürücüsü gerektirir. Veri kaynağınıza ait sürücü düzey 1 API kümesine uygunsa, yalnızca güncelleştirilebilir ve salt okunurdur ve salt-kayıt kümelerini ve yalnızca yukarı kayıt kümelerini kullanmaya devam edebilirsiniz. Ancak, düzey 1 bir sürücü genişletilmiş getirme ve anahtar kümesi temelli imleçler destekliyorsa dinamik kümeleri destekleyebilir. ODBC Uyumluluk düzeyleri hakkında daha fazla bilgi için bkz. [ODBC](../../data/odbc/odbc-basics.md).

> [!NOTE]
> Hem anlık görüntüleri hem de dinamik kümeleri kullanmak istiyorsanız, bunları iki farklı `CDatabase` nesneye (iki farklı bağlantı) dayandırmalısınız.

ODBC imleç kitaplığı tarafından tutulan ara depolamayı kullanan anlık görüntülerin aksine, dinamik kümeler, doğrudan veri kaynağından, ona doğru bir kayıt getirir. Bu, özgün değişken tarafından seçilen kayıtları veri kaynağıyla eşitlenmiş halde tutar.

Bu Visual C++ sürümünde yer alan ODBC sürücülerinin bir listesi ve ek sürücü alma hakkında bilgi için bkz. [ODBC sürücü listesi](../../data/odbc/odbc-driver-list.md).

## <a name="see-also"></a>Ayrıca bkz.

[Açık veritabanı bağlantısı (ODBC)](../../data/odbc/open-database-connectivity-odbc.md)
