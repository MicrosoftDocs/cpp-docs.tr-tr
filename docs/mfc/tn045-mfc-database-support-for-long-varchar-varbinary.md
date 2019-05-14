---
title: 'TN045: Uzun Varchar-Varbinary için MFC-veritabanı desteği'
ms.date: 11/04/2016
helpviewer_keywords:
- TN045
- Varbinary data type
- Varchar data type
ms.assetid: cf572c35-5275-45b5-83df-5f0e36114f40
ms.openlocfilehash: 3e8b356027e5c5b7c604a0354624d9f11e32fb9a
ms.sourcegitcommit: 934cb53fa4cb59fea611bfeb9db110d8d6f7d165
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65611041"
---
# <a name="tn045-mfcdatabase-support-for-long-varcharvarbinary"></a>TN045: Uzun Varchar/Varbinary için MFC/veritabanı desteği

> [!NOTE]
>  Aşağıdaki Teknik Not çevrimiçi belgelere ilk eklenmiştir beri güncelleştirilmemiş. Eski veya yanlış sonuç olarak, bazı yordamlar ve konular olabilir. En son bilgiler için bu konuyu çevrimiçi belge dizininde arama önerilir.

Bu not almak ve ODBC göndermek nasıl açıklar **SQL_LONGVARCHAR** ve **SQL_LONGVARBINARY** veri türleri kullanılarak MFC veritabanı sınıfları.

## <a name="overview-of-long-varcharvarbinary-support"></a>Uzun Varchar/Varbinary desteğine genel bakış

ODBC **SQL_LONG_VARCHAR** ve **SQL_LONGBINARY** veri türleri (burada uzun veri sütunları adlandırılır), büyük miktarlarda verinin tutabilir. Bu verileri işleyebilirsiniz 3 yolu vardır:

- Öğeyi bir `CString` / `CByteArray`.

- Öğeyi bir `CLongBinary`.

- Değil tüm bağlama almak ve uzun veri değeri el ile veritabanı sınıflarını bağımsız gönderin.

Her üç yöntemi, avantajları ve dezavantajları vardır.

Long veri sütunlar, sorgu parametreleri için desteklenmez. Bunlar yalnızca outputColumns için desteklenir.

## <a name="binding-a-long-data-column-to-a-cstringcbytearray"></a>Long veri sütunu bir CString/CByteArray bağlama

Avantajları:

Bu yaklaşım anlamak basit bir işlemdir ve tanıdık sınıflarla çalışır. Bir çerçeve sağlar `CFormView` desteği `CString` ile `DDX_Text`. Genel dize veya toplama işleviyle çok sayıda sahip `CString` ve `CByteArray` sınıfları ve yerel olarak veri değerini tutmak için ayrılan bellek miktarını denetleyebilirsiniz. Framework alan oluşturma sırasında yerleşim verilerine eski bir kopyasını tutar `Edit` veya `AddNew` işlev çağrıları ve verilerde yapılan değişiklikleri sizin için otomatik olarak algıla framework olabilir.

> [!NOTE]
>  Bu yana `CString` karakter verileri üzerinde çalışmak için tasarlanmıştır ve `CByteArray` ikili veriler üzerinde çalışmak için karakter verileri yerleştirmek önerilir (**SQL_LONGVARCHAR**) içine `CString`ve ikili verileri ( **SQL_LONGVARBINARY**) içine `CByteArray`.

RFX işlevleri için `CString` ve `CByteArray` olanak sağlayan veri sütununun alınan değerini tutmak için ayrılmış bellek varsayılan boyutu geçersiz kılma ek bir bağımsız değişkene sahip. Aşağıdaki işlev bildirimleri nMaxLength değişkeninde dikkat edin:

```
void AFXAPI RFX_Text(CFieldExchange* pFX,
    const char *szName,
    CString& value,
    int nMaxLength = 255,
    int nColumnType =
    SQL_VARCHAR);

void AFXAPI RFX_Binary(CFieldExchange* pFX,
    const char *szName,
    CByteArray& value,
    int nMaxLength = 255);
```

Long veri sütununa alırsanız bir `CString` veya `CByteArray`, maksimum veri miktarı, varsayılan olarak, 255 bayt döndürülür. Bu dışında herhangi bir şey yok sayılır. Bu durumda, çerçeve, özel durum oluşturur **AFX_SQL_ERROR_DATA_TRUNCATED**. Neyse ki, açıkça büyük değerlere nMaxLength kadar artırabilirsiniz **MAXINT**.

> [!NOTE]
>  NMaxLength değerini yerel arabelleğin ayarlamak için MFC tarafından kullanılan `SQLBindColumn` işlevi. Bu veri depolama için yerel önbellek ve ODBC sürücüsü tarafından döndürülen veri miktarını gerçekten etkilemez. `RFX_Text` ve `RFX_Binary` yalnızca bir çağrıda olun `SQLFetch` arka uç veritabanından veri almak için. Her ODBC sürücüsü, içinde tek bir getirme döndürmeleri veri miktarı üzerinde farklı bir sınırlama mevcuttur. Bu sınırı özel durumda nMaxLength ayarlamak değerinden daha küçük **AFX_SQL_ERROR_DATA_TRUNCATED** oluşturulur. Bu koşullar altında geçmesi `RFX_LongBinary` yerine `RFX_Text` veya `RFX_Binary` böylece tüm verileri alınabilir.

ClassWizard bağlama bir **SQL_LONGVARCHAR** için bir `CString`, veya bir **SQL_LONGVARBINARY** için bir `CByteArray` sizin için. Long veri sütununuzu almanızı 255 bayttan daha fazla ayırmak istiyorsanız, ardından nMaxLength için açıkça bir değer sağlayabilirsiniz.

Ne zaman bir uzun veri sütunu bağlı bir `CString` veya `CByteArray`, tıpkı bir SQL_ için ne zaman bağlı olarak bir alanı güncelleştirme çalışır**VARCHAR** veya SQL_**VARBINARY**. Sırasında `Edit`, veri değeri yerine ve daha sonra zaman karşılaştırıldığında önbelleğe `Update` verilerde yapılan değişiklikleri, değer ve kirli ayarlayın ve sütun değerleri uygun şekilde Null algılamak için çağrılır.

## <a name="binding-a-long-data-column-to-a-clongbinary"></a>Long veri sütunu için bir CLongBinary bağlama

Long veri sütununuzu daha içerebilir, **MAXINT** verileri baytlık, önünde bulundurmanız gereken büyük olasılıkla içine alınırken bir `CLongBinary`.

Avantajları:

Bu, kullanılabilir bellek kadar bir uzun tüm veri sütunu alır.

Olumsuz:

Veriler, bellekte tutulur. Bu yaklaşım da çok büyük miktarlardaki verilere yönelik fazla vakit pahalı olur. Çağırmalısınız `SetFieldDirty` bağlı veriler için alan emin olmak için üye yer aldığı bir `Update` işlemi.

Long veri sütunlara alırsanız bir `CLongBinary`, veritabanı sınıfları uzun veri sütununun toplam boyutunu kontrol edin ve ardından Ayır bir `HGLOBAL` bellek segmentinde tüm veri değeri tutabilecek kadar büyük. Veritabanı sınıfları daha sonra tüm veri değeri ayrılmış almak `HGLOBAL`.

Veri kaynağı, beklenen boyut uzun veri sütununun iade edemezsiniz, framework özel durum oluşturur **AFX_SQL_ERROR_SQL_NO_TOTAL**. Varsa tahsis girişimi `HGLOBAL` başarısız standart bellek özel durumu oluşturulur.

ClassWizard bağlama bir **SQL_LONGVARCHAR** veya **SQL_LONGVARBINARY** için bir `CLongBinary` sizin için. Seçin `CLongBinary` değişken türü olarak üye değişkeni Ekle iletişim kutusu. ClassWizard ardından ekleyecek bir `RFX_LongBinary` çağrısı, `DoFieldExchange` çağırın ve ilişkili alanların toplam sayısını artırın.

Uzun veri sütun değerleri güncelleştirmek için önce ayrılmış emin `HGLOBAL` çağırarak yeni verilerinizi tutmak için büyük **:: GlobalSize** üzerinde *m_hData* üyesi `CLongBinary`. Depolayamayacak kadar küçükse, yayın `HGLOBAL` ve uygun boyutta bir ayırın. Ardından *m_dwDataLength* yeni boyut yansıtacak şekilde.

Aksi takdirde *m_dwDataLength* boyuttan daha büyük değiştirerek verileri, ya da ücretsiz yeniden ayırın ve `HGLOBAL`, veya ayrılmış bırakın. İçinde gerçekten kullanılan bayt sayısını belirtmek emin *m_dwDataLength*.

## <a name="how-updating-a-clongbinary-works"></a>Bir CLongBinary güncelleştirme nasıl çalışır

Anlamak için gerekli değil nasıl güncelleştiren bir `CLongBinary` çalışır, ancak olabilir uzun veri değerlerini bir veri kaynağına göndermek nasıl bir örnek olarak yararlı aşağıda açıklanan bu üçüncü yöntemi seçerseniz.

> [!NOTE]
>  Sırayla bir `CLongBinary` bir güncelleştirme olarak dahil edilecek alan açıkça çağırmalıdır `SetFieldDirty` alan için. Null ayarı içeren bir alan için herhangi bir değişiklik yaparsanız çağırmalısınız `SetFieldDirty`. Ayrıca çağırmalıdır `SetFieldNull`, ikinci parametre olan ile **FALSE**, alanın bir değere sahip olarak işaretlemek için.

Güncelleştirirken bir `CLongBinary` alan, ODBC veritabanı sınıfları kullanın **DATA_AT_EXEC** mekanizması (ODBC belgelerine bakın `SQLSetPos`'s rgbValue bağımsız değişkeni). Ne zaman framework hazırlar işaret yerine INSERT nebo update deyimi `HGLOBAL` verilerini içeren *adresi* , `CLongBinary` olarak ayarlandığından *değer* sütun Bunun yerine ve kümesine uzunluğu göstergesi **SQL_DATA_AT_EXEC**. Daha sonra güncelleştirme bildirimi veri kaynağı için gönderildiğinde `SQLExecDirect` döndüreceği **SQL_NEED_DATA**. Bu sütun için parametre değeri gerçekten adresi olduğunu framework bu uyarı bir `CLongBinary`. Framework çağrıları `SQLGetData` kez küçük bir arabellek ile gerçek veri uzunluğu döndürülecek sürücü bekleniyor. Sürücü ikili büyük nesne (BLOB) gerçek uzunluğunu döndürürse, MFC kadar alanı BLOB getirmek için gerektiği şekilde yeniden ayırır. Veri kaynağı döndürür **SQL_NO_TOTAL**, BLOB boyutu belirlenemiyor gösteren, MFC daha küçük bir blok oluşturur. Varsayılan başlangıç boyutu 64 K'dır ve sonraki blokları iki katına olacaktır; Örneğin, ikinci 128 K, üçüncü 256 K ve bu şekilde devam eder. Başlangıç boyutu yapılandırılabilir.

## <a name="not-binding-retrievingsending-data-directly-from-odbc-with-sqlgetdata"></a>Bağlama değil: ODBC SQLGetData ile doğrudan veri alma/gönderme

Bu yöntem, tamamen atlama veritabanı sınıfları ile uzun veri sütununun kendiniz Dağıt.

Avantajları:

Gerekiyorsa, disk veya dinamik olarak ne kadar veri almak için karar vermek için verileri önbelleğe alabilir.

Olumsuz:

Framework'ün elde etmezsiniz `Edit` veya `AddNew` desteği ve yazmalıdır kendiniz temel işlevleri gerçekleştirmek için kod (`Delete` sütun düzeyi işlem olmadığından yine de çalışır).

Bu durumda, uzun veri sütununun kümesinin seçim listesinde olmalıdır, ancak için framework tarafından bağlanmalıdır değil. Yapmanın bir yolu aracılığıyla kendi SQL deyimi sağlamak budur `GetDefaultSQL` veya lpszSQL bağımsız değişkeni olarak `CRecordset`'s `Open` işlev ve bağlama RFX_ işlev çağrısıyla ek sütun yok. ODBC ilişkisiz alanlar ilişkili alanları sağında görünen gerektirir, bu nedenle bağlantısız sütun veya sütunlar select listesinin sonuna ekleyin.

> [!NOTE]
>  Long veri sütununuzu framework tarafından bağlı olmadığından, bu değişiklikler ile işlenmeyecek `CRecordset::Update` çağırır. Oluşturma ve gönderme gerekli SQL **Ekle** ve **güncelleştirme** deyimleri kendiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya Göre Teknik Notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)
