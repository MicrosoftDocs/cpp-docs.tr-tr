---
title: "TN045: Uzun Varchar Varbinary için MFC veritabanı desteği | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.data
dev_langs:
- C++
helpviewer_keywords:
- TN045
- Varbinary data type
- Varchar data type
ms.assetid: cf572c35-5275-45b5-83df-5f0e36114f40
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e1c9b64ef3b164c45a1633281bbaebd6525df659
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="tn045-mfcdatabase-support-for-long-varcharvarbinary"></a>TN045: Uzun Varchar/Varbinary için MFC/Veritabanı Desteği
> [!NOTE]
>  İlk çevrimiçi belgelerinde eklenmiştir beri aşağıdaki Teknik Not güncelleştirilmemiş. Sonuç olarak, bazı yordamlar ve konuları güncel veya yanlış olması olabilir. En son bilgiler için çevrimiçi belgeleri dizindeki ilgi konuyu aramak önerilir.  
  
 Bu not alın ve ODBC göndermek açıklar **SQL_LONGVARCHAR** ve **SQL_LONGVARBINARY** veri türleri kullanılarak MFC veritabanı sınıfları.  
  
## <a name="overview-of-long-varcharvarbinary-support"></a>Uzun Varchar/Varbinary desteği'ne genel bakış  
 ODBC **SQL_LONG_VARCHAR** ve **SQL_LONGBINARY** veri türleri (burada için uzun veri sütunlarını adlandırılır) çok büyük miktarlarda verinin basılı tutun. Bu veri işleyebilir 3 yolu vardır:  
  
-   Kendisine bağlı bir `CString` / `CByteArray`.  
  
-   Kendisine bağlı bir `CLongBinary`.  
  
-   Değil hiç bağlamak ve alabilir ve uzun veri değeri el ile veritabanı sınıflarını bağımsız gönderin.  
  
 Üç yöntemlerin her biri, avantajları ve dezavantajları vardır.  
  
 Long veri sütunları bir sorgu parametreleri için desteklenmiyor. Bunlar yalnızca outputColumns için desteklenir.  
  
## <a name="binding-a-long-data-column-to-a-cstringcbytearray"></a>CString/CLongBinary için uzun veri sütun bağlama  
 Avantajları:  
  
 Bu yaklaşımı anlamak basit bir işlemdir ve tanıdık sınıflarıyla çalışır. Bir çerçeve sağlar `CFormView` desteği `CString` ile `DDX_Text`. Çok sayıda genel dize veya toplama işleviyle sahip `CString` ve `CByteArray` sınıfları ve yerel olarak veri değeri tutmak için ayrılan bellek miktarını denetleyebilir. Framework alan verileri sırasında eski bir kopyasını tutar **Düzenle** veya `AddNew` işlev çağrılarını ve verilerde yapılan değişiklikleri sizin için otomatik olarak algıla framework olabilir.  
  
> [!NOTE]
>  Bu yana `CString` karakter verileri üzerinde çalışmak için tasarlanmış ve `CByteArray` ikili veriler üzerinde çalışmak için karakter verileri yerleştirme önerilir (**SQL_LONGVARCHAR**) içine `CString`ve (ikiliveriler **SQL_LONGVARBINARY**) içine `CByteArray`.  
  
 RFX işlevleri için `CString` ve `CByteArray` sağlayan alınan değerin veri sütununun tutmak için ayrılmış bellek varsayılan boyutu geçersiz kılma ek bağımsız değişken vardır. Aşağıdaki işlev bildirimleri nMaxLength değişkeninde dikkat edin:  
  
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
  
 Long veri sütununa alırsanız bir `CString` veya `CByteArray`, maksimum veri miktarı, varsayılan olarak, 255 bayt döndürülür. Bu ötesinde herhangi bir şey yok sayılır. Bu durumda, framework özel durum atar **AFX_SQL_ERROR_DATA_TRUNCATED**. Neyse ki, açıkça nMaxLength büyük değerlerine kadar artırabilirsiniz **MAXINT**.  
  
> [!NOTE]
>  NMaxLength değeri yerel arabelleğin ayarlamak için MFC tarafından kullanılan **SQLBindColumn** işlevi. Bu veri depolama için yerel önbellek ve gerçekte ODBC sürücüsü tarafından döndürülen veri miktarını etkilemez. `RFX_Text`ve `RFX_Binary` yalnızca birini kullanarak çağrısı yapmak **SQLFetch** arka uç veritabanından veri almak için. Her ODBC sürücüsü, tek bir getirme döndürmeleri veri miktarına farklı bir kısıtlaması vardır. Bu sınır, özel durumu case nMaxLength ayarlamak değerinden daha küçük **AFX_SQL_ERROR_DATA_TRUNCATED** oluşturulur. Bu koşullar altında kullanmaya geçiş `RFX_LongBinary` yerine `RFX_Text` veya `RFX_Binary` böylece tüm verileri alınabilir.  
  
 ClassWizard bağlamak bir **SQL_LONGVARCHAR** için bir `CString`, veya bir **SQL_LONGVARBINARY** için bir `CByteArray` sizin için. 255 uzun veri sütunu almak bayttan fazla ayırmak istiyorsanız, ardından nMaxLength için açık bir değer sağlayabilir.  
  
 Ne zaman uzun veri sütunu bağlı bir `CString` veya `CByteArray`, alan güncelleştirme çalışır tıpkı ne zaman bir SQL_ bağlı olarak**VARCHAR** veya SQL_**VARBINARY**. Sırasında **Düzenle**, veri değeri hemen ve daha sonra zaman karşılaştırıldığında önbelleğe **güncelleştirme** verilerde yapılan değişiklikleri değer Dirty ayarlamak ve sütun değerleri uygun şekilde Null algılamak için çağrılır.  
  
## <a name="binding-a-long-data-column-to-a-clongbinary"></a>Long veri sütunu bir CLongBinary bağlama  
 Long veri sütunu daha fazla bilgi içerebilir, **MAXINT** bayt veri, büyük olasılıkla düşünmelisiniz içine alınırken bir `CLongBinary`.  
  
 Avantajları:  
  
 Kullanılabilir bellek kadar bir tüm uzun veri sütunu alır.  
  
 Olumsuz yönleri:  
  
 Verileri bellekte tutulur. Bu yaklaşım, aynı zamanda şekilde basımı karşılamayacak kadar çok büyük miktarda veriyi pahalı olur. Çağırmalısınız `SetFieldDirty` ilişkili verileri alan emin olmak için üye yer aldığı bir **güncelleştirme** işlemi.  
  
 Long veri sütunlara alırsanız bir `CLongBinary`, veritabanı sınıfları uzun veri sütununun toplam boyutu denetleyin ve sonra tahsis bir `HGLOBAL` bellek kesimi tüm veri değeri tutabilecek kadar büyük. Veritabanı sınıfları ardından tüm veri değeri ayrılmış alacak `HGLOBAL`.  
  
 Veri kaynağı uzun veri sütununun beklenen boyut geri dönemezsiniz, framework özel durum atar **AFX_SQL_ERROR_SQL_NO_TOTAL**. Varsa tahsis girişimi `HGLOBAL` başarısız standart bellek özel durumu oluşur.  
  
 ClassWizard bağlamak bir **SQL_LONGVARCHAR** veya **SQL_LONGVARBINARY** için bir `CLongBinary` sizin için. Seçin `CLongBinary` üye değişken Ekle iletişim kutusunda değişken türü. ClassWizard sonra ekleyecek bir `RFX_LongBinary` çağrısı, `DoFieldExchange` çağırın ve ilişkili alan toplam sayısını artırın.  
  
 Uzun veri sütun değerleri güncelleştirmek için öncelikle ayrılmış emin olun `HGLOBAL` çağırarak yeni verilerinizi tutmak için yeterince büyük olduğundan **:: GlobalSize** üzerinde `m_hData` üyesi `CLongBinary`. Çok küçük ise, yayın `HGLOBAL` ve bir uygun boyutta ayırın. Ardından `m_dwDataLength` yeni boyutu yansıtacak şekilde.  
  
 Aksi halde, eğer `m_dwDataLength` boyuttan büyük değiştirerek verileri, ya da ücretsiz yeniden ayırın ve `HGLOBAL`, ayrılan bırakın. Gerçekte kullanılan bayt sayısını belirtmek emin `m_dwDataLength`.  
  
## <a name="how-updating-a-clongbinary-works"></a>Bir CLongBinary güncelleştirme nasıl çalışır  
 Anlamak gerekli değildir nasıl güncelleştiren bir `CLongBinary` çalışır, ancak olabileceği gibi bir veri kaynağına uzun veri değerleri gönderme konusunda bir örnek olarak yararlı aşağıda açıklanan bu üçüncü yöntemi seçerseniz.  
  
> [!NOTE]
>  Sırayla bir `CLongBinary` bir güncelleştirmede dahil edilecek alan açıkça çağırmalısınız `SetFieldDirty` alan için. Null, ayarı dahil olmak üzere bir alan için herhangi bir değişiklik yaparsanız çağırmalısınız `SetFieldDirty`. Ayrıca çağırmalısınız `SetFieldNull`, ikinci parametre olan ile **yanlış**, alanın bir değere sahip olarak işaretlemek için.  
  
 Güncelleştirilirken bir `CLongBinary` alan, veritabanı sınıflarını kullanma ODBC **DATA_AT_EXEC** mekanizması (ODBC belgelerine bakın **SQLSetPos**'s rgbValue bağımsız değişkeni). Ne zaman framework hazırlar işaret yerine INSERT veya update deyiminin `HGLOBAL` verileri içeren *adresi* , `CLongBinary` olarak ayarlanmış olan *değeri* sütunun Bunun yerine ve kümesine uzunluğu göstergesi **SQL_DATA_AT_EXEC**. Daha sonra veri kaynağına update deyiminin gönderildiğinde **SQLExecDirect** döndürülecek **SQL_NEED_DATA**. Bu sütun için parametre değeri gerçekte adresini olduğunu framework bu uyarıları bir `CLongBinary`. Framework çağrıları **SQLGetData** kez küçük bir arabellek verilerinin gerçek uzunluğuyla döndürmek için sürücü bekleniyor. Sürücü ikili büyük nesne (BLOB) gerçek uzunluğuyla döndürürse, MFC kadar alan BLOBU getirilmeye gerektiğinde yeniden ayırır. Veri kaynağı döndürür, **SQL_NO_TOTAL**, BLOB boyutu belirleyemiyor belirten, MFC küçük blokları oluşturur. Varsayılan başlangıç boyutu 64 K'dır ve sonraki blokları iki katına olacaktır; Örneğin, ikinci 128 K olacaktır, üçüncü 256 K ve benzeri. Başlangıç boyutu yapılandırılabilir.  
  
## <a name="not-binding-retrievingsending-data-directly-from-odbc-with-sqlgetdata"></a>Bağlama değil: Alma/verileri doğrudan ODBC SQLGetData ile gönderme  
 Bu yöntem, tamamen veritabanı sınıfları atlama ile uzun veri sütununun kendiniz ilgilenir.  
  
 Avantajları:  
  
 Gerekirse, disk veya dinamik olarak ne kadar veri almaya karar için verileri önbelleğe alabilir.  
  
 Olumsuz yönleri:  
  
 Framework'ün almadım **Düzenle** veya `AddNew` gerekir desteği ve yazma kendiniz temel işlevleri gerçekleştirmek için kod (**silmek** sütun düzeyi işlemi olmadığından yine de çalışır).  
  
 Bu durumda, uzun veri sütununun kayıt seçim listesinde olması gerekir, ancak için çerçevesi tarafından bağlanmalıdır değil. Yapmanın bir yolu, kendi SQL deyimi aracılığıyla sağlamak için budur `GetDefaultSQL` veya lpszSQL bağımsız değişkeni olarak `CRecordset`'s **açık** işlev ve ek sütunu RFX_ işlev çağrısı ile bağlı değil. ODBC ilişkisiz alanlar bağlı alanlar sağında görünür gerektirir, bu nedenle bağlantısız sütun veya sütunlar select listesinin sonuna ekleyin.  
  
> [!NOTE]
>  Long veri sütunu çerçevesi tarafından bağlı olmadığından yapılan değişikliklerin ile işleneceğini değil `CRecordset::Update` çağrıları. Oluşturma ve gerekli SQL Gönder **Ekle** ve **güncelleştirme** deyimleri kendiniz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sayıya göre teknik notlar](../mfc/technical-notes-by-number.md)   
 [Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)

