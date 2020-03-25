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
ms.openlocfilehash: ed7098600126005978c8b017e7db378fca4c1a68
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213245"
---
# <a name="dynaset"></a>Dynaset

Bu konuda, dinamik kümeler açıklanmakta ve [kullanılabilirlikleri](#_core_availability_of_dynasets)anlatılmaktadır.

> [!NOTE]
>  Bu konu, [CRecordset](../../mfc/reference/crecordset-class.md)dahil olmak üzere MFC ODBC sınıfları için geçerlidir. DAO sınıflarında dinamik kümeler hakkında daha fazla bilgi için bkz. [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md). DAO ile, değişken tür kayıt kümelerini açabilirsiniz.

DYNASET, dinamik özelliklere sahip bir kayıt kümesidir. Bağımsız değişken modundaki (genellikle Dynaset olarak adlandırılır) bir kayıt kümesi nesnesi, veri kaynağıyla aşağıdaki şekilde eşitlenmiş olarak kalır. Çok kullanıcılı bir ortamda, diğer kullanıcılar, dinamik kümenize ait kayıtları düzenleyebilir veya silebilir ya da Dynaset 'in gösterdiği tabloya kayıt ekleyebilirsiniz. Uygulamanızın kayıt kümesine eklediği veya kümeden sildiği kayıtlar, dinamik kümenize yansıtılır. Diğer kullanıcıların tabloya ekleyen kayıtlar, `Requery` üye işlevini çağırarak dinamik küme yeniden derlenene kadar dinamik kümenize yansıtılmayacaktır. Diğer kullanıcılar kayıtları sildiği zaman, MFC kodu kayıt kümenizde silmeleri atlar. Diğer kullanıcıların, var olan kayıtlarda değişiklik düzenlemesi, etkilenen kayda doğru kaydırdığınızda, dinamik kümenize yansıtılır.

Benzer şekilde, bir Dynaset içindeki kayıtlarda yaptığınız düzenlemeler, diğer kullanıcılar tarafından kullanılan dinamik kümeler halinde yansıtılır. Eklediğiniz kayıtlar, dinamik kümeleri yeniden sorgulanana kadar diğer kullanıcıların dinamik kümeleri ' ne yansıtılmaz. Sildiğiniz kayıtlar, diğer kullanıcıların kayıt kümelerinde "silindi" olarak işaretlenir. Aynı veritabanına (birden çok `CDatabase` nesnesi) birden çok bağlantınız varsa, bu bağlantılarla ilişkili kayıt kümeleri, diğer kullanıcıların kayıt kümeleriyle aynı duruma sahiptir.

Veri kümeleri, bir hava yolu ayırma sisteminde (örneğin) verilerin dinamik olması gerektiğinde en değerlidir.

> [!NOTE]
> Dinamik kümeleri kullanmak için, veri kaynağınız için dinamik kümeleri destekleyen bir ODBC sürücünüz olmalıdır ve ODBC imleç kitaplığı yüklenmemelidir. Daha fazla bilgi için bkz. [Dinamik kümeler kullanılabilirliği](#_core_availability_of_dynasets).

Bir kayıt kümesinin bir Dynaset olduğunu belirtmek için, `CRecordset::dynaset` kayıt kümesi nesnenizin `Open` üye işlevine ilk parametre olarak geçirin.

> [!NOTE]
> Güncelleştirilebilir dinamik kümeler için, ODBC sürücünüzün konumlandırılmış Update deyimlerini veya `::SQLSetPos` ODBC API işlevini desteklemesi gerekir. Her ikisi de destekleniyorsa, MFC verimlilik için `::SQLSetPos` kullanır.

##  <a name="availability-of-dynasets"></a><a name="_core_availability_of_dynasets"></a>Dinamik kümeler kullanılabilirliği

MFC veritabanı sınıfları, aşağıdaki gereksinimler karşılandığında dinamik kümeleri destekler:

- ODBC imleç kitaplığı DLL dosyası bu veri kaynağı için kullanımda olmamalıdır.

   İmleç kitaplığı kullanılıyorsa, küme kümesi desteği için gerekli olan temel ODBC sürücüsünün bazı işlevlerini maskeler. Dinamik kümeleri kullanmak istiyorsanız (ve ODBC sürücünüz, bu bölümün geri kalanında açıklandığı gibi, dinamik kümeler için gereken işlevlere sahipse), `CDatabase` nesnesi oluştururken MFC 'nin imleç kitaplığını yükleyememesine neden olabilirsiniz. Daha fazla bilgi için bkz. [ODBC](../../data/odbc/odbc-basics.md) ve [openex](../../mfc/reference/cdatabase-class.md#openex) veya `CDatabase`sınıfının [Açık](../../mfc/reference/cdatabase-class.md#open) üye işlevi.

   ODBC terminolojisinde, dinamik kümeler ve anlık görüntüler imleçler olarak adlandırılır. İmleç bir kayıt kümesindeki konumunu izlemek için kullanılan bir mekanizmadır.

- Veri kaynağınız için ODBC sürücüsü, anahtar kümesi temelli imleçleri desteklemelidir.

   Anahtar kümesi temelli imleçler bir anahtarlar kümesini alarak ve depolayarak bir tablodaki verileri yönetir. Anahtarlar, Kullanıcı belirli bir kayıt üzerinde kaydırıldığında tablodaki geçerli verileri almak için kullanılır. Sürücünüzün bu desteği sağladığını öğrenmek için, *SQL_SCROLL_OPTIONS* PARAMETRESIYLE `::SQLGetInfo` ODBC API işlevini çağırın.

   Anahtar kümesi desteği olmadan bir Dynaset açmaya çalışırsanız, dönüş kodu değeri AFX_SQL_ERROR_DYNASET_NOT_SUPPORTED bir `CDBException` alırsınız.

- Veri kaynağınız için ODBC sürücüsünün genişletilmiş getirme desteği gerekir.

   Genişletilmiş getirme, geriye doğru kaymanın yanı sıra SQL sorgunuzun sonuç kayıtlarını ileriye doğru kaydırabilme olanağıdır. Sürücünüzün bu özelliği destekleyip desteklemediğini anlamak için, *SQL_API_SQLEXTENDEDFETCH* PARAMETRESIYLE `::SQLGetFunctions` ODBC API işlevini çağırın.

Güncelleştirilebilir dinamik kümeleri (veya anlık görüntüleri) istiyorsanız, ODBC sürücünüz `::SQLSetPos` ODBC API işlevini veya konumlandırılmış güncelleştirmeleri de desteklemelidir. `::SQLSetPos` işlevi, MFC 'nin SQL deyimleri göndermeden veri kaynağını güncelleştirmesine izin verir. Bu destek varsa, MFC SQL kullanarak güncelleştirme yapmak için bunu tercih altında kullanır. Sürücünüzün `::SQLSetPos`destekleyip desteklemediğini öğrenmek için *SQL_POS_OPERATIONS* parametresiyle `::SQLGetInfo` çağırın.

Konumlandırılmış **güncelleştirmeler, veri** kaynağındaki tablodaki belirli bir satırı BELIRLEMEK için SQL söz dizimini (\<cursorname >) kullanır. Sürücünüzün konumlandırılmış güncelleştirmeleri destekleyip desteklemediğini öğrenmek için *SQL_POSITIONED_STATEMENTS* parametresiyle `::SQLGetInfo` çağırın.

Genellikle MFC dinamik kümeleri (yalnızca iletme kayıt kümeleri), düzey 2 API uyumluluğu olan bir ODBC sürücüsü gerektirir. Veri kaynağınıza ait sürücü düzey 1 API kümesine uygunsa, yalnızca güncelleştirilebilir ve salt okunurdur ve salt-kayıt kümelerini ve yalnızca yukarı kayıt kümelerini kullanmaya devam edebilirsiniz. Ancak, düzey 1 bir sürücü genişletilmiş getirme ve anahtar kümesi temelli imleçler destekliyorsa dinamik kümeleri destekleyebilir. ODBC Uyumluluk düzeyleri hakkında daha fazla bilgi için bkz. [ODBC](../../data/odbc/odbc-basics.md).

> [!NOTE]
> Hem anlık görüntüleri hem de dinamik kümeleri kullanmak istiyorsanız, bunları iki farklı `CDatabase` nesnesine dayandırmalısınız (iki farklı bağlantı).

ODBC imleç kitaplığı tarafından tutulan ara depolamayı kullanan anlık görüntülerin aksine, dinamik kümeler, doğrudan veri kaynağından, ona doğru bir kayıt getirir. Bu, özgün değişken tarafından seçilen kayıtları veri kaynağıyla eşitlenmiş halde tutar.

Visual C++ 'in bu sürümünde yer alan ODBC sürücülerinin bir listesi ve ek sürücü alma hakkında bilgi için bkz. [ODBC sürücü listesi](../../data/odbc/odbc-driver-list.md).

## <a name="see-also"></a>Ayrıca bkz.

[Açık Veritabanı Bağlantısı (ODBC)](../../data/odbc/open-database-connectivity-odbc.md)
