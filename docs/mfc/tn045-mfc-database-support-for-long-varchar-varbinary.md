---
title: 'TN045: Uzun Varchar-Varbinary için MFC-Veritabanı Desteği'
ms.date: 11/04/2016
helpviewer_keywords:
- TN045
- Varbinary data type
- Varchar data type
ms.assetid: cf572c35-5275-45b5-83df-5f0e36114f40
ms.openlocfilehash: 55a68ba970d0a26163f426d51818c701c13ed051
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81750284"
---
# <a name="tn045-mfcdatabase-support-for-long-varcharvarbinary"></a>TN045: Uzun Varchar/Varbinary için MFC/Veritabanı Desteği

> [!NOTE]
> Aşağıdaki teknik not, çevrimiçi belgelere ilk olarak eklenmediğinden beri güncelleştirilemedi. Sonuç olarak, bazı yordamlar ve konular güncel veya yanlış olabilir. En son bilgiler için, çevrimiçi belge dizini ilgi alanı için arama nız önerilir.

Bu not, MFC veritabanı sınıflarını kullanarak ODBC **SQL_LONGVARCHAR** ve **SQL_LONGVARBINARY** veri türlerinin nasıl alınıp gönderilen açıklar.

## <a name="overview-of-long-varcharvarbinary-support"></a>Uzun Varchar/Varikili Desteğe Genel Bakış

ODBC **SQL_LONG_VARCHAR** ve **SQL_LONGBINARY** veri türleri (burada uzun veri sütunları olarak adlandırılır) büyük miktarda veri tutabilir. Bu verileri işlemenin 3 yolu vardır:

- Bir `CString` / `CByteArray`.

- Bir `CLongBinary`.

- Veritabanı sınıflarından bağımsız olarak uzun veri değerini el ile alıp göndermeyin.

Her üç yöntem avantajları ve dezavantajları vardır.

Uzun veri sütunları, sorguparametreleri için desteklenmez. Bunlar yalnızca çıktılar Için DesteklenirSütunlar.

## <a name="binding-a-long-data-column-to-a-cstringcbytearray"></a>Uzun Veri Sütunu CString/CByteArray'e Bağlama

Artılar:

Bu yaklaşımı anlamak kolaydır ve tanıdık sınıflarla çalışırsınız. Çerçeve ile `CFormView` `CString` `DDX_Text`destek sağlar. Ve `CString` `CByteArray` sınıflarla birlikte çok sayıda genel dize veya toplama işleviniz vardır ve veri değerini tutmak için yerel olarak ayrılan bellek miktarını denetleyebilirsiniz. Çerçeve, arama sırasında veya `Edit` `AddNew` işlev çağrıları sırasında alan verilerinin eski bir kopyasını tutar ve çerçeve sizin için verilerdeki değişiklikleri otomatik olarak algılayabilir.

> [!NOTE]
> `CString` Karakter verileri üzerinde çalışmak `CByteArray` ve ikili veriler üzerinde çalışmak için tasarlandığından, karakter verilerini **(SQL_LONGVARCHAR)** ve ikili verileri `CString` `CByteArray`**(SQL_LONGVARBINARY)** içine koymanız önerilir.

RFX, veri `CString` `CByteArray` sütunu için alınan değeri tutmak için ayrılan belleğin varsayılan boyutunu geçersiz kılmanıza olanak tanıyan ek bir bağımsız değişken için çalışır ve vardır. Aşağıdaki işlev bildirimlerinde nMaxLength bağımsız değişkenine dikkat edin:

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

Uzun bir veri sütununu `CString` bir `CByteArray`veya , döndürülen maksimum veri miktarı na alırsanız, varsayılan olarak 255 bayt olur. Bunun ötesindeki her şey göz ardı edilir. Bu durumda, çerçeve **AFX_SQL_ERROR_DATA_TRUNCATED**özel durum atacaktır. Neyse ki, nMaxLength'ı **maxint'e**kadar daha büyük değerlere açıkça artırabilirsiniz.

> [!NOTE]
> nMaxLength değeri `SQLBindColumn` fonksiyonun yerel arabellek ayarlamak için MFC tarafından kullanılır. Bu, verilerin depolanması için yerel arabellektir ve gerçekte ODBC sürücüsü tarafından döndürülen veri miktarını etkilemez. `RFX_Text`ve `RFX_Binary` verileri arka `SQLFetch` uç veritabanından almak için yalnızca bir arama yapın. Her ODBC sürücüsü, tek bir getirmede döndürebilecekleri veri miktarı yla ilgili farklı bir sınırlamaya sahiptir. Bu sınır nMaxLength'ta ayarlanan değerden çok daha küçük olabilir ve bu durumda özel durum **AFX_SQL_ERROR_DATA_TRUNCATED** atılır. Bu koşullar altında, `RFX_LongBinary` tüm `RFX_Text` verilerin `RFX_Binary` alınabilmesi için yerine kullanmaya geçin.

ClassWizard bir **SQL_LONGVARCHAR** `CString`bir veya bir **SQL_LONGVARBINARY** `CByteArray` sizin için bağlayacak. Uzun veri sütununuzu aldığınız 255'ten fazla bayt ayırmak istiyorsanız, nMaxLength için açık bir değer sağlayabilirsiniz.

Uzun bir veri sütunu `CString` bir `CByteArray`veya , alan güncelleştirme bağlı olduğunda bir SQL_**VARCHAR** veya SQL_**VARBINARY**bağlı olduğu gibi çalışır. Sırasında, `Edit`veri değeri önbelleğe alınıp, `Update` veri değerindeki değişiklikleri algılamak ve sütun için Kirli ve Null değerlerini uygun şekilde ayarlamak için çağrıldığında karşılaştırılır.

## <a name="binding-a-long-data-column-to-a-clongbinary"></a>Uzun Veri Sütununu CLongBinary'ye Bağlama

Uzun veri sütununuz daha fazla **MAXINT** bayt veri içeriyorsa, büyük `CLongBinary`olasılıkla bir .

Artılar:

Bu, kullanılabilir belleğe kadar tüm uzun bir veri sütunu alır.

Eksileri:

Veriler bellekte tutulur. Bu yaklaşım, çok büyük miktarda veri için de son derece pahalıdır. Alanın bir `SetFieldDirty` `Update` işlemde yer aldığından emin olmak için bağlı veri üyesini aramanız gerekir.

Uzun veri sütunlarını bir `CLongBinary`, veritabanı sınıfları uzun veri sütununun toplam boyutunu `HGLOBAL` denetler, ardından tüm veri değerini tutacak kadar büyük bir bellek kesimi ayırır. Veritabanı sınıfları daha sonra ayrılan içine `HGLOBAL`tüm veri değeri almak.

Veri kaynağı uzun veri sütununun beklenen boyutunu döndüremezse, çerçeve özel durum **AFX_SQL_ERROR_SQL_NO_TOTAL.** Başarısız ayırma girişimi `HGLOBAL` başarısız olursa, standart bir bellek özel durum atılır.

ClassWizard sizin için bir **SQL_LONGVARBINARY** `CLongBinary` **SQL_LONGVARCHAR** veya SQL_LONGVARBINARY bağlayacak. Üye `CLongBinary` Değişken Ekle iletişim kutusunda Değişken Türü olarak seçin. ClassWizard daha sonra `RFX_LongBinary` çağrınıza `DoFieldExchange` bir çağrı ekler ve bağlı alanların toplam sayısını artırır.

Uzun veri sütunu değerlerini güncelleştirmek için, öncelikle ayrılan ın yeni verilerinizi tutabilecek kadar `HGLOBAL` büyük `CLongBinary`olduğundan emin **olun: "GlobalSize,** *m_hData* üye. Çok küçükse, `HGLOBAL` bırakın ve uygun boyutu ayırın. Sonra yeni boyutu yansıtacak *şekilde m_dwDataLength* ayarlayın.

Aksi takdirde, *m_dwDataLength* değiştirdiğiniz verinin boyutundan daha büyükse, ya serbest `HGLOBAL`bırakabilir ve yeniden tahsis edebilirsiniz. *m_dwDataLength'da*fiilen kullanılan bayt sayısını belirttiğinden emin olun.

## <a name="how-updating-a-clongbinary-works"></a>CLongBinary Nasıl Çalışır Güncelleme

Bir güncelleştirmenin nasıl `CLongBinary` çalıştığını anlamak gerekli değildir, ancak aşağıda açıklanan bu üçüncü yöntemi seçerseniz, bir veri kaynağına uzun veri değerlerinin nasıl gönderilecek lerine ilişkin bir örnek olarak yararlı olabilir.

> [!NOTE]
> Bir `CLongBinary` alanın güncelleştirmeye dahil edilebilmesi için, alanı `SetFieldDirty` açıkça aramanız gerekir. Null ayarı da dahil olmak üzere bir alanda herhangi `SetFieldDirty`bir değişiklik yaparsanız, aramanız gerekir. Ayrıca, ikinci `SetFieldNull`parametre **FALSE**olan , alanı bir değere sahip olarak işaretlemek için de aramalısınız.

Bir `CLongBinary` alanı güncellerken, veritabanı sınıfları ODBC'nin **DATA_AT_EXEC** mekanizmasını `SQLSetPos`kullanır ('rgbValue bağımsız değişkeni ile ilgili ODBC belgelerine bakın). Çerçeve, ekleme veya güncelleştirme deyimini hazırlarken, verileri `HGLOBAL` içerene işaret etmek `CLongBinary` yerine, sütunun *adresi* ve **SQL_DATA_AT_EXEC**için uzunluk göstergesi olarak ayarlanır. *value* Daha sonra, güncelleştirme deyimi veri kaynağına `SQLExecDirect` gönderildiğinde, **SQL_NEED_DATA**döndürür. Bu, bu sütun için param değeri aslında bir `CLongBinary`. Çerçeve, `SQLGetData` sürücünün verilerin gerçek uzunluğunu döndürmesini bekleyerek küçük bir arabellekle bir kez çağırır. Sürücü ikili büyük nesnenin (BLOB) gerçek uzunluğunu döndürürse, MFC BLOB'u getirmek için gerektiği kadar alanı yeniden tahsis eder. Veri kaynağı **SQL_NO_TOTAL**döndürürse, BLOB'un boyutunu belirleyemeyeceğini gösterirse, MFC daha küçük bloklar oluşturur. Varsayılan başlangıç boyutu 64K'dır ve sonraki bloklar iki katı boyutta olacaktır; örneğin, ikinci 128K olacak, üçüncü 256K, ve benzeri. İlk boyut yapılandırılabilir.

## <a name="not-binding-retrievingsending-data-directly-from-odbc-with-sqlgetdata"></a>Bağlayıcı Değil: SQLGetData ile Doğrudan ODBC'den Veri Alma/Gönderme

Bu yöntemle veritabanı sınıflarını tamamen atlayın ve uzun veri sütunuyla kendiniz ilgilenin.

Artılar:

Gerekirse verileri diske olarak önbelleğe alabilir veya ne kadar veri alınacağına dinamik olarak karar verebilirsiniz.

Eksileri:

Çerçevenin `Edit` veya `AddNew` desteğin ini alamazsınız ve temel işlevselliği gerçekleştirmek için`Delete` kod kendiniz yazmanız gerekir (sütun düzeyinde bir işlem olmadığı için işe yarar).

Bu durumda, uzun veri sütunu kayıt kümesinin seçili listesinde olmalıdır, ancak çerçeveye bağlı olmamalıdır. Bunu yapmanın bir yolu, lpszSQL `GetDefaultSQL` bağımsız değişkeni aracılığıyla veya `CRecordset`'işlevi olarak kendi SQL bildiriminizi sağlamak ve ek sütunu RFX_ bir işlev çağrısıyla `Open` bağlamamaktır. ODBC, bağlı olmayan alanların bağlı alanların sağında görünmesini gerektirir, bu nedenle bağlanmamış sütununuzu veya sütunlarınızı seçme listesinin sonuna ekleyin.

> [!NOTE]
> Uzun veri sütununuz çerçeveye bağlı olmadığından, bu sütundaki `CRecordset::Update` değişiklikler aramalarla işlenmez. Gerekli SQL **INSERT** ve **UPDATE** ifadelerini kendiniz oluşturmalı ve göndermelisiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya Göre Teknik Notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)
