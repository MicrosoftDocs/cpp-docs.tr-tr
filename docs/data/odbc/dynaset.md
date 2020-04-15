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
ms.openlocfilehash: 2eb2447d1f984b7734d5e9c45087023e5a6f003f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371836"
---
# <a name="dynaset"></a>Dynaset

Bu konu dynasets açıklar ve [bunların durumu](#_core_availability_of_dynasets)tartışır.

> [!NOTE]
> Bu konu [CRecordset](../../mfc/reference/crecordset-class.md)de dahil olmak üzere MFC ODBC sınıfları için geçerlidir. DAO sınıflarında dinamitler hakkında daha fazla bilgi için [CDaoRecordset'e](../../mfc/reference/cdaorecordset-class.md)bakın. DAO ile dynaset tipi kayıt kümelerini açabilirsiniz.

Dynaset dinamik özelliklere sahip bir kayıt kümesidir. Ömrü boyunca, dynaset modunda (genellikle dinamit olarak adlandırılır) bir kayıt kümesi nesnesi aşağıdaki şekilde veri kaynağı ile senkronize kalır. Çok kullanıcılı bir ortamda, diğer kullanıcılar dinamitinizdeki kayıtları düzenleyebilir veya silebilir veya dinamitinizin temsil ettiği tabloya kayıt ekleyebilir. Uygulamanızın kayıt kümesine eklediği veya sildiği kayıtlar dinamitinize yansıtılır. Diğer kullanıcıların tabloya ekleyen kayıtları, `Requery` üye işlevini arayarak dinamiti yeniden yapılandırana kadar dinamitinize yansıtılmayacaktır. Diğer kullanıcılar kayıtları sildiğinde, MFC kodu kayıt setinizdeki silmeleri atlar. Etkilenen kayda geçer kaydırır kaydırMaz diğer kullanıcıların varolan kayıtlardaki düzenleme değişiklikleri dinamitinize yansıtılır.

Benzer şekilde, bir dinamitteki kayıtlara yaptığınız düzenleme, diğer kullanıcılar tarafından kullanılan dinamitlere yansıtılır. Eklediğiniz kayıtlar, dinamitlerini yeniden sorgulayına kadar diğer kullanıcıların dinamitlerine yansıtılmaz. Sildiğiniz kayıtlar diğer kullanıcıların kayıt kümelerinde "silinmiş" olarak işaretlenir. Aynı veritabanına (birden çok `CDatabase` nesne) birden çok bağlantınız varsa, bu bağlantılarla ilişkili kayıt kümeleri diğer kullanıcıların kayıt kümeleriyle aynı duruma sahiptir.

Dinamsetleri, bir havayolu rezervasyon sisteminde (örneğin) olduğu gibi, verilerin dinamik olması gerektiğinde en değerli olanlardır.

> [!NOTE]
> Dynasets kullanmak için, dinamit leri destekleyen veri kaynağınız için bir ODBC sürücüsüne sahip olmalısınız ve ODBC imleç kitaplığı yüklenmemelidir. Daha fazla bilgi için [Dynasets'in kullanılabilirliği](#_core_availability_of_dynasets)bölümüne bakın.

Kayıt kümesinin bir dinamit olduğunu `CRecordset::dynaset` belirtmek için, kayıt `Open` kümesi nesnenizin üye işlevine ilk parametre olarak geçin.

> [!NOTE]
> Günceldama dinamitleri için, ODBC sürücünüzün konumlandırılmış güncelleştirme deyimlerini veya `::SQLSetPos` ODBC API işlevini desteklemesi gerekir. Her ikisi de desteklenirse, MFC verimlilik için kullanır. `::SQLSetPos`

## <a name="availability-of-dynasets"></a><a name="_core_availability_of_dynasets"></a>Dynaset'in Kullanılabilirliği

Aşağıdaki gereksinimler karşılanırsa MFC veritabanı sınıfları dinamitleri destekler:

- ODBC imleç kitaplığı DLL bu veri kaynağı için kullanılmamalıdır.

   İmleç kitaplığı kullanılırsa, dinaset desteği için gerekli olan altta yatan ODBC sürücüsünün bazı işlevlerini maskeler. Damaset kullanmak istiyorsanız (ve ODBC sürücünüz, bu bölümün geri kalanında açıklandığı gibi dinamitler için gerekli işlevsellik lere sahiptir), bir `CDatabase` nesne oluştururken MFC'nin imleç kitaplığını yüklememesine neden olabilirsiniz. Daha fazla bilgi için [Bkz. ODBC](../../data/odbc/odbc-basics.md) ve [OpenEx](../../mfc/reference/cdatabase-class.md#openex) `CDatabase`veya [Sınıfın Open](../../mfc/reference/cdatabase-class.md#open) üye işlevi.

   ODBC terminolojisinde, dinamitler ve anlık görüntülerimleç olarak adlandırılır. İmleç, bir kayıt kümesindeki konumunu izlemek için kullanılan bir mekanizmadır.

- Veri kaynağınızın ODBC sürücüsü anahtar kümesi yle çalışan imleçleri desteklemelidir.

   Anahtar kümesi yle çalışan imleçler, bir dizi anahtar alıp depolayarak tablodaki verileri yönetir. Anahtarlar, kullanıcı belirli bir kayda kaydırıldığında tablodan geçerli verileri elde etmek için kullanılır. Sürücünüzün bu desteği sağlayıp `::SQLGetInfo` sağlamadığını belirlemek *için, SQL_SCROLL_OPTIONS* parametresi ile ODBC API işlevini arayın.

   Anahtar seti desteği olmadan bir dinaset açmaya `CDBException` çalışırsanız, AFX_SQL_ERROR_DYNASET_NOT_SUPPORTED iade kodu değeri ile bir a elde elabilirsiniz.

- Veri kaynağınız için ODBC sürücüsü genişletilmiş alma desteği gerekir.

   Genişletilmiş alma, SQL sorgunuzun ortaya çıkan kayıtları üzerinde geriye ve ileriye kaydırma olanağıdır. Sürücünüzün bu yeteneği destekleyip `::SQLGetFunctions` desteklemediğini belirlemek *için, SQL_API_SQLEXTENDEDFETCH* parametresi ile ODBC API işlevini arayın.

Güncelleştirilebilir dynasets (veya anlık görüntü, bu konuda) istiyorsanız, ODBC `::SQLSetPos` sürücüsü de ODBC API işlevi veya konumlandırılmış güncelleştirmeleri desteklemesi gerekir. İşlev, MFC'nin `::SQLSetPos` SQL deyimleri göndermeden veri kaynağını güncelleştirmesine olanak tanır. Bu destek varsa, MFC bunu SQL kullanarak güncelleştirmeler yapmak için kullanır. Sürücünüzün destekleyip `::SQLSetPos`desteklemediğini belirlemek için `::SQLGetInfo` *SQL_POS_OPERATIONS* parametresini arayın.

Konumlandırılmış güncelleştirmeler, veri kaynağındaki tablodaki belirli bir satırı tanımlamak için SQL sözdizimini **(IMLECnamenin CURRENT OF** \<>) kullanılmasını kullanır. Sürücünüzün konumlandırılmış güncelleştirmeleri destekleyip desteklemediğini belirlemek için `::SQLGetInfo` *SQL_POSITIONED_STATEMENTS* parametresini arayın.

Genellikle, MFC dynasets (ancak sadece ileri kayıt setleri) düzey 2 API uyumlu bir ODBC sürücüsü gerektirir. Veri kaynağınızın sürücüsü düzey 1 API kümesine uyuyorsa, dynasets değil, hem güncelleştirilebilir hem de salt okunur anlık görüntüleri ve yalnızca ileri kayıt kümelerini kullanabilirsiniz. Ancak, bir düzey 1 sürücü genişletilmiş getirme ve anahtar kümesi tahrikli imleçleri destekliyorsa dinamitleri destekleyebilir. ODBC uygunluk düzeyleri hakkında daha fazla bilgi için [ODBC'ye](../../data/odbc/odbc-basics.md)bakın.

> [!NOTE]
> Hem anlık görüntüleri hem de dynaset'i kullanmak istiyorsanız, `CDatabase` bunları iki farklı nesneye (iki farklı bağlantı) dayandırmalısınız.

ODBC imleç kitaplığı tarafından tutulan ara depolamayı kullanan anlık görüntünün aksine, dinamitler bir kaydı doğrudan veri kaynağından getirir. Bu, başlangıçta veri kaynağı ile senkronize dinamit tarafından seçilen kayıtları tutar.

Visual C++ bu sürümünde yer alan ODBC sürücülerinin listesi ve ek sürücü edinme hakkında bilgi için [Bkz. ODBC Sürücü Listesi.](../../data/odbc/odbc-driver-list.md)

## <a name="see-also"></a>Ayrıca bkz.

[Açık Veritabanı Bağlantısı (ODBC)](../../data/odbc/open-database-connectivity-odbc.md)
