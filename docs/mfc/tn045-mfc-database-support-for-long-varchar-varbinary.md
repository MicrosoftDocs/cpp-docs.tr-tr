---
description: 'Hakkında daha fazla bilgi edinin: TN045: Long varchar/varbinary için MFC/veritabanı desteği'
title: 'TN045: uzun Varchar-Varbinary MFC-Database desteği'
ms.date: 11/04/2016
helpviewer_keywords:
- TN045
- Varbinary data type
- Varchar data type
ms.assetid: cf572c35-5275-45b5-83df-5f0e36114f40
ms.openlocfilehash: 4e19147ab5ca392307f331b12d3cf24eb5fcc06f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97215189"
---
# <a name="tn045-mfcdatabase-support-for-long-varcharvarbinary"></a>TN045: Uzun Varchar/Varbinary için MFC/Veritabanı Desteği

> [!NOTE]
> Aşağıdaki teknik Not, çevrimiçi belgelere ilk eklenmesinden beri güncelleştirilmemiş. Sonuç olarak, bazı yordamlar ve konular güncel olmayabilir veya yanlış olabilir. En son bilgiler için çevrimiçi belge dizininde ilgilendiğiniz konuyu aramanız önerilir.

Bu notta, MFC veritabanı sınıflarını kullanarak ODBC **SQL_LONGVARCHAR** ve **SQL_LONGVARBINARY** veri türlerinin nasıl alınacağını ve gönderileceğini açıklanır.

## <a name="overview-of-long-varcharvarbinary-support"></a>Uzun varchar/varbinary desteğine genel bakış

ODBC **sql_long_varchar** ve **SQL_LONGBINARY** veri türleri (burada uzun veri sütunları olarak adlandırılır) çok büyük miktarlarda veri tutabilir. Bu verileri işleyebilmeniz için 3 yol vardır:

- Bir öğesine bağlayın `CString` / `CByteArray` .

- Bir öğesine bağlayın `CLongBinary` .

- Onu hiç bağlamayın ve uzun veri değerini, veritabanı sınıflarından bağımsız olarak el ile alın ve gönderin.

Üç yöntemin her biri avantajları ve dezavantajlara sahiptir.

Bir sorguya yönelik parametreler için uzun veri sütunları desteklenmez. Yalnızca outputColumns için desteklenir.

## <a name="binding-a-long-data-column-to-a-cstringcbytearray"></a>Uzun veri sütununu CString/CByteArray öğesine bağlama

Artılar:

Bu yaklaşım anlaşılması basittir ve tanıdık sınıflarla çalışırsınız. Framework `CFormView` ile için destek sağlar `CString` `DDX_Text` . Ve sınıflarıyla çok sayıda genel dize veya koleksiyon işlevi vardır `CString` `CByteArray` ve veri değerini tutmak için yerel olarak ayrılan bellek miktarını kontrol edebilirsiniz. Çerçeve, veya işlev çağrıları sırasında alan verilerinin eski bir kopyasını tutar `Edit` `AddNew` ve çerçeve sizin için verilerde yapılan değişiklikleri otomatik olarak algılayabilir.

> [!NOTE]
> `CString`, Karakter verilerinde çalışmak için tasarlandığından ve `CByteArray` ikili veriler üzerinde çalışmak için, karakter verilerini (**SQL_LONGVARCHAR**) `CString` ve ikili verileri (**SQL_LONGVARBINARY**) içine koymanız önerilir `CByteArray` .

İçin RFX işlevleri `CString` ve `CByteArray` veri sütunu için alınan değeri tutmak üzere ayrılan belleğin varsayılan boyutunu geçersiz kılabilmenizi sağlayan ek bir bağımsız değişkeni vardır. Aşağıdaki işlev bildirimlerinde nMaxLength bağımsız değişkenine göz önünde edin:

```cpp
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

Bir veya ' a uzun veri sütunu alırsanız, `CString` `CByteArray` en fazla döndürülen veri miktarı varsayılan olarak 255 bayttır. Bunun ötesinde herhangi bir şey yok sayılır. Bu durumda, çerçeve **afx_sql_error_data_truncated** özel durumu oluşturur. Neyse ki, en fazla **maxint** olmak üzere nMaxLength 'i daha büyük değerler olarak artırabilirsiniz.

> [!NOTE]
> NMaxLength değeri, işlevin yerel arabelleğini ayarlamak için MFC tarafından kullanılır `SQLBindColumn` . Bu, verilerin depolanması için yerel arabellekte bulunur ve aslında ODBC sürücüsü tarafından döndürülen veri miktarını etkilemez. `RFX_Text` ve `RFX_Binary` yalnızca `SQLFetch` , arka uç veritabanından veri almak için kullanarak bir çağrı yapın. Her ODBC sürücüsünün tek bir getirme işleminde döndürebilecekleri veri miktarına farklı bir sınırlaması vardır. Bu sınır nMaxLength ' de ayarlanan değerden çok daha küçük olabilir, bu durumda özel durum **afx_sql_error_data_truncated** atılır. Bu koşullarda, `RFX_LongBinary` `RFX_Text` tüm verilerin alınabilmesi için veya yerine kullanma ' ya geçiş yapın `RFX_Binary` .

ClassWizard  `CString` , sizin için bir SQL_LONGVARCHAR veya **SQL_LONGVARBINARY** bir ' a bağlayacaktır `CByteArray` . Uzun veri sütununuzu aldığınız 255 bayttan fazlasını ayırmak istiyorsanız, nMaxLength için açık bir değer sağlayabilirsiniz.

Bir veya uzun bir veri sütunu bir `CString` veya ' a bağlandığında `CByteArray` , alanı güncelleştirmek yalnızca bir sql_ **varchar** veya sql_ **VARBINARY** öğesine bağlandığına göre aynı şekilde çalışacaktır. Sırasında `Edit` veri değeri, `Update` veri değerinde yapılan değişiklikleri algılamak ve sütun için kirli ve null değerlerini ayarlamak üzere çağrıldığında, daha sonra önbelleğe alınır ve daha sonra karşılaştırılır.

## <a name="binding-a-long-data-column-to-a-clongbinary"></a>Uzun veri sütununu bir CLongBinary 'ye bağlama

Uzun veri sütunlarınız daha fazla **MaxInt** bayt veri içeriyorsa, büyük olasılıkla bunu bir öğesine almayı göz önünde bulundurmanız gerekir `CLongBinary` .

Artılar:

Bu, tüm uzun veri sütununu kullanılabilir belleğe kadar alır.

Eksileri:

Veriler bellekte tutulur. Bu yaklaşım çok büyük miktarlarda veri için de canlı maliyetli hale getirmektedir. `SetFieldDirty`Alanın bir işleme dahil edildiğinden emin olmak için, bağlantılı veri üyesini çağırmanız gerekir `Update` .

' A uzun veri sütunları alırsanız `CLongBinary` , veritabanı sınıfları uzun veri sütununun toplam boyutunu kontrol eder ve ardından bir `HGLOBAL` bellek segmentini tüm veri değerini tutacak büyüklükte ayırır. Veritabanı sınıfları daha sonra tüm veri değerini ayrılmış olarak alır `HGLOBAL` .

Veri kaynağı uzun veri sütununun beklenen boyutunu döndüremiyorsa, çerçeve **afx_sql_error_sql_no_total** özel durumu oluşturur. Ayırma girişimi `HGLOBAL` başarısız olursa standart bir bellek özel durumu oluşturulur.

ClassWizard, sizin için bir **SQL_LONGVARCHAR** veya **SQL_LONGVARBINARY** bağlayacaktır `CLongBinary` . `CLongBinary`Üye değişkeni Ekle iletişim kutusunda değişken türü olarak öğesini seçin. Classınterm Sihirbazı daha sonra `RFX_LongBinary` çağrımya bir çağrı ekleyecek `DoFieldExchange` ve toplam bağlantılı alan sayısını artıracaktır.

Uzun veri sütunu değerlerini güncelleştirmek için, önce ayrılan değerin `HGLOBAL` , *m_hData* üyesinde **:: GlobalSize** çağırarak, yeni verilerinizi tutmak için yeterince büyük olduğundan emin olun `CLongBinary` . Çok küçükse, serbest bırakın `HGLOBAL` ve uygun boyutta bir tane ayırın. Ardından *m_dwDataLength* yeni boyutu yansıtacak şekilde ayarlayın.

Aksi takdirde, *m_dwDataLength* değiştirdiğiniz verilerin boyutundan daha büyükse, ' yi serbest bırakıp yeniden tahsis edebilir `HGLOBAL` ya da ayrılmış olursunuz. *M_dwDataLength*' de gerçekten kullanılan bayt sayısını belirttiğinizden emin olun.

## <a name="how-updating-a-clongbinary-works"></a>Bir CLongBinary 'Nin güncelleştirilmesi

Bir çalışma güncelleştirmesini anlamak gerekli değildir `CLongBinary` , ancak aşağıda açıklanan üçüncü yöntemi seçerseniz bir veri kaynağına uzun veri değerleri gönderme hakkında bir örnek olarak yararlı olabilir.

> [!NOTE]
> Bir `CLongBinary` alanın bir güncelleştirmeye dahil edilmesi için, alanı açıkça çağırmanız gerekir `SetFieldDirty` . Bir alanda değişiklik yaparsanız, null ayarı da dahil olmak üzere, öğesini çağırmanız gerekir `SetFieldDirty` . Ayrıca, `SetFieldNull` değeri bir değere sahip olacak şekilde işaretlemek için ikinci parametresi **false** olarak da çağırmanız gerekir.

Bir alanı güncelleştirirken `CLongBinary` , veritabanı SıNıFLARı ODBC 'nin **data_at_exec** mekanizmasını kullanır (bkz `SQLSetPos` . rgbValue bağımsız değişkeni üzerinde ODBC belgeleri). Çerçeve INSERT veya Update ifadesini, verileri içeren içine işaret etmek yerine, ' `HGLOBAL` nin *adresi* , `CLongBinary` sütunun *değeri* olarak ayarlanır ve uzunluk göstergesi **sql_data_at_exec** olarak ayarlanır. Daha sonra, Update ifadesinin veri kaynağına gönderilmesi `SQLExecDirect` **sql_need_data** döndürür. Bu, bu sütun için param değerinin gerçekten bir adresi olduğunu gösteren çerçeveyi uyarır `CLongBinary` . Çerçeve, `SQLGetData` küçük bir arabellekle bir kez çağırır ve sürücünün gerçek veri uzunluğunu döndürmesi bekleniyor. Sürücü, ikili büyük nesne (BLOB) gerçek uzunluğunu döndürürse, MFC, blobu getirmek için gereken kadar fazla alan bulur. Veri kaynağı **SQL_NO_TOTAL** DÖNDÜRÜRSE, blob 'un boyutunu BELIRLEYEMEYECEĞINI belirten MFC daha küçük bloklar oluşturur. Varsayılan başlangıç boyutu 64K ve sonraki bloklar boyutu iki katına alınır; Örneğin, ikincisi 128K, üçüncüsü ise ve bu şekilde devam eder. Başlangıç boyutu yapılandırılabilir.

## <a name="not-binding-retrievingsending-data-directly-from-odbc-with-sqlgetdata"></a>Bağlama değil: SQLGetData ile doğrudan ODBC 'den veri alma/gönderme

Bu yöntemle, veritabanı sınıflarını tamamen atlar ve uzun veri sütunuyla birlikte işlem yapabilirsiniz.

Artılar:

Gerekirse verileri diske önbelleğe alabilir veya ne kadar veri alınacağını dinamik olarak seçebilirsiniz.

Eksileri:

Framework 'ün `Edit` veya `AddNew` desteğinin yanı sıra temel işlevleri gerçekleştirmek için de kod yazmanız gerekir ( `Delete` bir sütun düzeyi işlem olmadığından, ancak çalışır).

Bu durumda, uzun veri sütunu, kayıt kümesinin seçim listesinde olmalıdır, ancak Framework tarafından bağlanmamalıdır. Bunu yapmanın bir yolu, kendi SQL deyiminizi `GetDefaultSQL` veya `CRecordset` `Open` bir RFX_ işlev çağrısıyla birlikte ek sütununu bağlamayın. ODBC, bağlantılı alanların sağında ilişkisiz alanların görünmesini gerektirir, bu nedenle, bağlı olmayan sütununuzu veya sütunlarınızı seçim listesinin sonuna ekleyin.

> [!NOTE]
> Uzun veri sütunlarınız Framework tarafından bağlanmadığından, üzerinde yapılan değişiklikler `CRecordset::Update` çağrılarla işlenmeyecektir. Gerekli SQL **Insert** ve **Update** deyimlerini kendiniz oluşturmanız ve göndermeniz gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya göre teknik notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye göre teknik notlar](../mfc/technical-notes-by-category.md)
