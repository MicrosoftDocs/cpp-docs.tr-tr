---
title: COleCurrency sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleCurrency
- AFXDISP/COleCurrency
- AFXDISP/COleCurrency::COleCurrency
- AFXDISP/COleCurrency::Format
- AFXDISP/COleCurrency::GetStatus
- AFXDISP/COleCurrency::ParseCurrency
- AFXDISP/COleCurrency::SetCurrency
- AFXDISP/COleCurrency::SetStatus
- AFXDISP/COleCurrency::m_cur
- AFXDISP/COleCurrency::m_status
dev_langs:
- C++
helpviewer_keywords:
- COleCurrency [MFC], COleCurrency
- COleCurrency [MFC], Format
- COleCurrency [MFC], GetStatus
- COleCurrency [MFC], ParseCurrency
- COleCurrency [MFC], SetCurrency
- COleCurrency [MFC], SetStatus
- COleCurrency [MFC], m_cur
- COleCurrency [MFC], m_status
ms.assetid: 3a36e345-303f-46fb-a57c-858274378a8d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b8139047f47a1984dca9faba3ebff6b0426bb444
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="colecurrency-class"></a>COleCurrency sınıfı
Yalıtan `CURRENCY` OLE Otomasyon veri türü.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class COleCurrency  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleCurrency::COleCurrency](#colecurrency)|Oluşturan bir `COleCurrency` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleCurrency::Format](#format)|Biçimlendirilmiş dize gösterimini oluşturur bir `COleCurrency` nesnesi.|  
|[COleCurrency::GetStatus](#getstatus)|Bu durum (geçerlilik) alır `COleCurrency` nesnesi.|  
|[COleCurrency::ParseCurrency](#parsecurrency)|Okuyan bir **para birimi** bir dizeden değer ve değeri ayarlar `COleCurrency`.|  
|[COleCurrency::SetCurrency](#setcurrency)|Bu değeri ayarlar `COleCurrency` nesnesi.|  
|[COleCurrency::SetStatus](#setstatus)|Durum (geçerlilik) Bu ayarlar `COleCurrency` nesnesi.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[işleç =](#operator_eq)|Kopya bir `COleCurrency` değeri.|  
|[operator +, -](#operator_plus_minus)|Ekler, çıkarır ve değişiklikleri belirtisi `COleCurrency` değerleri.|  
|[operator +=-=](#operator_plus_minus_eq)|Ekler ve çıkarır bir `COleCurrency` bu değerden `COleCurrency` nesnesi.|  
|[işleç * /](#operator_star)|Ölçek bir `COleCurrency` bir tamsayı değeri.|  
|[işleç * = / =](#operator_star_div_eq)|Bu ölçeklendirir `COleCurrency` bir tamsayı değeri.|  
|[işleç <<](#operator_stream)|Çıkış bir `COleCurrency` değeri `CArchive` veya `CDumpContext`.|  
|[İşleç >>](#operator_stream)|Girişleri bir `COleCurrency` nesnesinin `CArchive`.|  
|[para birimi işleci](#operator_currency)|Dönüştüren bir `COleCurrency` içine değeri bir **para birimi**.|  
|[operator ==, <, < =, vb..](#colecurrency_relational_operators)|İki karşılaştırır `COleCurrency` değerleri.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleCurrency::m_cur](#m_cur)|Arka plandaki içeren **para birimi** bu `COleCurrency` nesnesi.|  
|[COleCurrency::m_status](#m_status)|Bu durumu içeren `COleCurrency` nesnesi.|  
  
## <a name="remarks"></a>Açıklamalar  
 **COleCurrency** bir taban sınıfı yok.  
  
 **Para birimi** 8 bayt, 10.000 ölçeğinde ikiye tamsayı değeri olarak uygulanır. Bu seçenek, bir sabit noktalı ondalık ayırıcının sol tarafındaki 15 basamağa numarasıyla ve 4 basamak sağa sağlar. **Para birimi** veri türü olan veya tüm sabit noktalı hesaplama para içeren hesaplamalar için son derece kullanışlı doğruluğunu önemli olduğu. Olası türlerinde biridir `VARIANT` OLE Otomasyon veri türü.  
  
 **COleCurrency** de bu sabit noktalı türü için aritmetik bazı temel işlemleri uygular. Sabit noktalı hesaplamalar sırasında ortaya yuvarlama hataları denetlemek için desteklenen işlemler seçilmedi.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `COleCurrency`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdisp.h  
  
##  <a name="colecurrency"></a>  COleCurrency::COleCurrency  
 Oluşturan bir **COleCurrency** nesnesi.  
  
```  
COleCurrency();  
COleCurrency(CURRENCY cySrc);  
  COleCurrency(const COleCurrency& curSrc);  
COleCurrency(const VARIANT& varSrc);

 
COleCurrency(
    long nUnits,  
    long nFractionalUnits);
```  
  
### <a name="parameters"></a>Parametreler  
 `cySrc`  
 A **para birimi** yeni içine kopyalanacak değeri **COleCurrency** nesnesi.  
  
 `curSrc`  
 Var olan **COleCurrency** yeni içine kopyalanacak nesne **COleCurrency** nesnesi.  
  
 *varSrc*  
 Var olan **değişken** veri yapısı (büyük olasılıkla bir `COleVariant` nesnesi) bir para birimi değeri dönüştürülecek ( `VT_CY`) ve yeni içine kopyalanan **COleCurrency** nesnesi.  
  
 `nUnits`, `nFractionalUnits`  
 Birimleri ve kesirli kısmını değeri (1/10, 000's)'daki yeni içine kopyalanacak belirtmek **COleCurrency** nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Tüm bu oluşturucular Yeni Oluştur **COleCurrency** nesneleri belirtilen değerle başlatılır. Bu oluşturucu her kısa bir açıklamasını izler. Aksi belirtilmediği sürece, yeni durumunu **COleCurrency** öğesi için geçerli ayarlanır.  
  
- COleCurrency() yapıları bir **COleCurrency** nesne 0 (sıfır) başlatıldı.  
  
- COleCurrency (`cySrc`) oluşturan bir **COleCurrency** nesnesinin bir [para birimi](http://msdn.microsoft.com/en-us/5e81273c-7289-45c7-93c0-32c1553f708e) değeri.  
  
- COleCurrency (`curSrc`) oluşturan bir **COleCurrency** varolan bir nesne **COleCurrency** nesnesi. Yeni bir nesne kaynak nesne ile aynı duruma sahiptir.  
  
- COleCurrency (`varSrc`) oluşturan bir **COleCurrency** nesnesi. Dönüştürmeye çalışır bir [değişken](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118) yapısı veya `COleVariant` bir para birimi nesnesine ( `VT_CY`) değeri. Bu dönüştürme başarılı olursa, dönüştürülen değer yeni içine kopyalanır **COleCurrency** nesnesi. Değeri, değilse **COleCurrency** nesne ayarlanmış sıfır (0) ve onun durumu geçersiz.  
  
- `COleCurrency(`nUnits`, `nFractionalUnits') oluşturan bir **COleCurrency** belirtilen sayısal bileşenlerinden nesnesi. Kesirli bölümü mutlak değerini 10. 000 ' büyükse, uygun düzeltme birimlerine yapılır. Birimleri ve kesirli bölümü tarafından imzalanan uzun değerler belirtilen unutmayın.  
  
 Daha fazla bilgi için bkz: [para birimi](http://msdn.microsoft.com/en-us/5e81273c-7289-45c7-93c0-32c1553f708e) ve [değişken](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118) Windows SDK'sı giriş.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnekler sıfır parametresi ve iki parametresi oluşturucular etkileri gösterir:  
  
 [!code-cpp[NVC_MFCOleContainer#10](../../mfc/codesnippet/cpp/colecurrency-class_1.cpp)]  
  
##  <a name="format"></a>  COleCurrency::Format  
 Para birimi değeri biçimlendirilmiş bir temsilini oluşturmak için bu üye işlevini çağırın.  
  
```  
CString Format(DWORD  dwFlags = 0, LCID  lcid = LANG_USER_DEFAULT) const; 
```  
  
### <a name="parameters"></a>Parametreler  
 `dwFlags`  
 Yerel ayarlar için bayrakları belirtir. Yalnızca aşağıdaki bayrağı para birimi için geçerlidir:  
  
- **LOCALE_NOUSEROVERRIDE** özel kullanıcı ayarları yerine sistem varsayılan yerel ayarları kullanın.  
  
 `lcid`  
 Dönüştürme işlemi için kullanılacak yerel ayar Kimliğini gösterir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `CString` biçimlendirilmiş para birimi değeri içerir.  
  
### <a name="remarks"></a>Açıklamalar  
 Yerel dil belirtimleri (yerel ayar kimlikleri) kullanarak değeri biçimlendirir. Para birimi simgesini döndürülen değer dahil edilmez. Varsa bu durumu **COleCurrency** nesnesi null, boş bir dize dönüş değeri değil. Geçersiz durumundaysa, dönüş dizesi dize kaynak tarafından belirtilen **IDS_INVALID_CURRENCY**.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCOleContainer#11](../../mfc/codesnippet/cpp/colecurrency-class_2.cpp)]  
  
##  <a name="getstatus"></a>  COleCurrency::GetStatus  
 (Geçerlilik) durumunu almak için bu üye işlevini çağırın bir verilen **COleCurrency** nesnesi.  
  
```  
CurrencyStatus GetStatus() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu durumu döndürür **COleCurrency** değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Dönüş değeri tarafından tanımlanan `CurrencyStatus` numaralandırılmış içinde tanımlanan türü **COleCurrency** sınıfı.  
  
```  
enum CurrencyStatus {
    valid = 0,
    invalid = 1,
    null = 2
    };  
```  
  
 Bu durum değerleri kısa bir açıklaması için aşağıdaki listeye bakın:  
  
- **COleCurrency::valid** belirtir bu **COleCurrency** nesne geçerlidir.  
  
- **COleCurrency::invalid** belirtir bu **COleCurrency** nesnesi geçersiz; diğer bir deyişle, değeri yanlış olabilir.  
  
- **COleCurrency::null** belirtir bu **COleCurrency** nesnesi null, diğer bir deyişle, bu nesne için herhangi bir değer belirtildi. (Bu bir "herhangi bir değer aksine C++ kullanılmasının" veritabanı algılama "null" **NULL**.)  
  
 Durumunu bir **COleCurrency** nesnesi aşağıdaki durumlarda geçersiz:  
  
-   Gelen değerini ayarlarsanız bir **değişken** veya `COleVariant` bir para birimi değeri dönüştürülemedi değeri.  
  
-   Bu nesne bir taşması veya underflow aritmetik atama işlemi sırasında örneğin karşılaştı, `+=` veya **\* =**.  
  
-   Bu nesne için geçersiz bir değer atanmışsa.  
  
-   Kullanarak geçersiz bu nesnenin durumu açıkça ayarlanmış olmadığını [SetStatus](#setstatus).  
  
 İşlemler hakkında daha fazla bilgi için aşağıdaki üye işlevlerini geçersiz bkz durumu ayarlayabilir:  
  
- [COleCurrency](#colecurrency)  
  
- [işleç =](#operator_eq)  
  
- [operator + -](#operator_plus_minus)  
  
- [operator += ve-=](#operator_plus_minus_eq)  
  
- [işleç * /](#operator_star)  
  
- [işleç * = ve / =](#operator_star_div_eq)  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCOleContainer#12](../../mfc/codesnippet/cpp/colecurrency-class_3.cpp)]  
  
##  <a name="m_cur"></a>  COleCurrency::m_cur  
 Arka plandaki [para birimi](http://msdn.microsoft.com/en-us/5e81273c-7289-45c7-93c0-32c1553f708e) bu yapısı **COleCurrency** nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
  
> [!CAUTION]
>  Değer değiştirme **para birimi** bu işlev tarafından döndürülen işaretçi tarafından erişilen yapısı, bu değeri değiştirir **COleCurrency** nesnesi. Bu durumu değiştirmez **COleCurrency** nesnesi.  
  
 Daha fazla bilgi için bkz: [para birimi](http://msdn.microsoft.com/en-us/5e81273c-7289-45c7-93c0-32c1553f708e) Windows SDK'sı giriş.  
  
##  <a name="m_status"></a>  COleCurrency::m_status  
 Bu veri üyesi türü numaralandırılmış türüdür `CurrencyStatus`, içinde tanımlanan **COleCurrency** sınıfı.  
  
```  
enum CurrencyStatus{  
    valid = 0,  
    invalid = 1,  
    null = 2,  
};  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu durum değerleri kısa bir açıklaması için aşağıdaki listeye bakın:  
  
- **COleCurrency::valid** belirtir bu **COleCurrency** nesne geçerlidir.  
  
- **COleCurrency::invalid** belirtir bu **COleCurrency** nesnesi geçersiz; diğer bir deyişle, değeri yanlış olabilir.  
  
- **COleCurrency::null** belirtir bu **COleCurrency** nesnesi null, diğer bir deyişle, bu nesne için herhangi bir değer belirtildi. (Bu bir "herhangi bir değer aksine C++ kullanılmasının" veritabanı algılama "null" **NULL**.)  
  
 Durumunu bir **COleCurrency** nesnesi aşağıdaki durumlarda geçersiz:  
  
-   Gelen değerini ayarlarsanız bir **değişken** veya `COleVariant` bir para birimi değeri dönüştürülemedi değeri.  
  
-   Bu nesne bir taşması veya underflow aritmetik atama işlemi sırasında örneğin karşılaştı, `+=` veya **\* =**.  
  
-   Bu nesne için geçersiz bir değer atanmışsa.  
  
-   Kullanarak geçersiz bu nesnenin durumu açıkça ayarlanmış olmadığını [SetStatus](#setstatus).  
  
 İşlemler hakkında daha fazla bilgi için aşağıdaki üye işlevlerini geçersiz bkz durumu ayarlayabilir:  
  
- [COleCurrency](#colecurrency)  
  
- [işleç =](#operator_eq)  
  
- [operator +, -](#operator_plus_minus)  
  
- [operator +=-=](#operator_plus_minus_eq)  
  
- [işleç * /](#operator_star)  
  
- [işleç * = / =](#operator_star_div_eq)  
  
    > [!CAUTION]
    >  Gelişmiş programlama durumlar için bu veri üyesidir. Satır içi üye işlevleri kullanması gereken [GetStatus](#getstatus) ve [SetStatus](#setstatus). Bkz: `SetStatus` açıkça bu veri üyesi ayarlama ile ilgili daha fazla uyarılar için.  
  
##  <a name="operator_eq"></a>  COleCurrency::operator =  
 Bu aşırı yüklenmiş atama işleçleri kaynak para birimi değeri bu kopyalamak **COleCurrency** nesnesi.  
  
```  
const COleCurrency& operator=(CURRENCY cySrc);  
const COleCurrency& operator=(const COleCurrency& curSrc);  
  const COleCurrency& operator=(const VARIANT& varSrc);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Her işleç kısa bir açıklamasını aşağıdaki gibidir:  
  
- **işleç = (** `cySrc` **)** `CURRENCY` değeri kopyalanır **COleCurrency** nesne ve durumu ayarlanmış için geçerli.  
  
- **işleç = (** `curSrc` **)** değeri ve var olan işleneni durumunu **COleCurrency** nesne bu aralığa kopyalanır **COleCurrency** nesnesi .  
  
- **işleç = (** *varSrc* **)** varsa dönüştürülmesi `VARIANT` değeri (veya [COleVariant](../../mfc/reference/colevariant-class.md) nesne) bir para birimi için ( `VT_CY`) olan başarılı, dönüştürülen değer bu kopyalanır **COleCurrency** nesne ve durumu ayarlanmış için geçerli. Dönüştürme başarılı değilse değerini **COleCurrency** nesne ayarlanmış 0 ve durumu geçersiz.  
  
 Daha fazla bilgi için bkz: [para birimi](http://msdn.microsoft.com/en-us/5e81273c-7289-45c7-93c0-32c1553f708e) ve [değişken](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118) Windows SDK'sı giriş.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCOleContainer#15](../../mfc/codesnippet/cpp/colecurrency-class_4.cpp)]  
  
##  <a name="operator_plus_minus"></a>  COleCurrency::operator +, -  
 Bu işleçlere ekleme ve iki izin **COleCurrency** değerleri için ve birbirlerinden ve işaretini değiştirmek için bir **COleCurrency** değeri.  
  
```  
COleCurrency operator+(const COleCurrency& cur) const;  
COleCurrency operator-(const COleCurrency& cur) const;  
COleCurrency operator-() const;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 İşlenen birini ise null, elde edilen durumunu **COleCurrency** değeri NULL'dur.  
  
 Aritmetik işlemin taşar varsa, elde edilen **COleCurrency** değeri geçersiz.  
  
 İşlenen geçersiz ve diğer null, elde edilen durumunu ise **COleCurrency** değeri geçersiz.  
  
 Geçerli, geçersiz ve null durum değerleri hakkında daha fazla bilgi için bkz: [m_status](#m_status) üye değişkeni.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCOleContainer#16](../../mfc/codesnippet/cpp/colecurrency-class_5.cpp)]  
  
##  <a name="operator_plus_minus_eq"></a>  COleCurrency::operator +=-=  
 Ekleme ve çıkarma olanak tanıyan bir **COleCurrency** için ve bu değer **COleCurrency** nesnesi.  
  
```  
const COleCurrency& operator+=(const COleCurrency& cur);  
const COleCurrency& operator-=(const COleCurrency& cur);
```  
  
### <a name="remarks"></a>Açıklamalar  
 İşlenen birini ise null, bu durumu **COleCurrency** nesne ayarlanmış null.  
  
 Aritmetik işlemin taşar varsa, bu durumu **COleCurrency** kümesi nesnesi geçersiz.  
  
 İşlenen birini geçersiz ve diğer null değilse, bu durumu **COleCurrency** nesne ayarlanmış geçersiz.  
  
 Geçerli, geçersiz ve null durum değerleri hakkında daha fazla bilgi için bkz: [m_status](#m_status) üye değişkeni.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCOleContainer#17](../../mfc/codesnippet/cpp/colecurrency-class_6.cpp)]  
  
##  <a name="operator_star"></a>  COleCurrency::operator * ve /  
 Ölçeklendirmenizi izin bir **COleCurrency** değer bir tamsayı değeri.  
  
```  
COleCurrency operator*(long nOperand) const;  
COleCurrency operator/(long nOperand) const;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa **COleCurrency** işleneni null, elde edilen durumunu **COleCurrency** değeri NULL'dur.  
  
 Aritmetik işlemin taşarsa veya sayımında, elde edilen durumunu **COleCurrency** değeri geçersiz.  
  
 Varsa **COleCurrency** işlenen geçersiz sonuç durumunu **COleCurrency** değeri geçersiz.  
  
 Geçerli, geçersiz ve null durum değerleri hakkında daha fazla bilgi için bkz: [m_status](#m_status) üye değişkeni.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCOleContainer#18](../../mfc/codesnippet/cpp/colecurrency-class_7.cpp)]  
  
##  <a name="operator_star_div_eq"></a>  COleCurrency::operator * = / =  
 Bu ölçeklendirmenizi izin **COleCurrency** değer bir tamsayı değeri.  
  
```  
const COleCurrency& operator*=(long nOperand);  
const COleCurrency& operator/=(long nOperand);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa **COleCurrency** işleneni null, bu durumu **COleCurrency** nesne ayarlanmış null.  
  
 Aritmetik işlemin taşar varsa, bu durumu **COleCurrency** kümesi nesnesi geçersiz.  
  
 Varsa **COleCurrency** işlenen geçersiz bu durumu **COleCurrency** kümesi nesnesi geçersiz.  
  
 Geçerli, geçersiz ve null durum değerleri hakkında daha fazla bilgi için bkz: [m_status](#m_status) üye değişkeni.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCOleContainer#19](../../mfc/codesnippet/cpp/colecurrency-class_8.cpp)]  
  
##  <a name="operator_stream"></a>  COleCurrency::operator &lt; &lt;, &gt;&gt;  
 Tanılama dökme ve arşive depolama destekler.  
  
```  
friend CDumpContext& operator<<(
    CDumpContext& dc,  
    COleCurrency curSrc);
 
friend CArchive& operator<<(
    CArchive& ar,  
    COleCurrency curSrc);
 
friend CArchive& operator>>(
    CArchive& ar,  
    COleCurrency& curSrc);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Ayıklama ( **>>**) işleci bir arşiv yüklenmesini destekler.  
  
##  <a name="operator_currency"></a>  COleCurrency::operator para birimi  
 Döndürür bir `CURRENCY` değeri öğesinden kopyalanır yapısı **COleCurrency** nesnesi.  
  
```  
operator CURRENCY() const; 
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="parsecurrency"></a>  COleCurrency::ParseCurrency  
 Para birimi değeri okumak için bir dizeyi ayrıştırmak için bu üye işlevini çağırın.  
  
```  
BOOL ParseCurrency(
    LPCTSTR lpszCurrency,  
    DWORD dwFlags = 0,  
    LCID lcid = LANG_USER_DEFAULT);
 
throw(CMemoryException*); 
throw(COleException*);
```  
  
### <a name="parameters"></a>Parametreler  
 *lpszCurrency*  
 Ayrıştırılacak olan null ile sonlandırılmış dize için bir işaretçi.  
  
 `dwFlags`  
 Yerel ayarları, büyük olasılıkla aşağıdaki bayrağı bayrakları gösterir:  
  
- **LOCALE_NOUSEROVERRIDE** özel kullanıcı ayarları yerine sistem varsayılan yerel ayarları kullanın.  
  
 `lcid`  
 Dönüştürme işlemi için kullanılacak yerel ayar Kimliğini gösterir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dize para birimi değeri için Aksi halde 0 başarıyla dönüştürüldü, sıfır olmayan.  
  
### <a name="remarks"></a>Açıklamalar  
 Kaynak dizesi sayısal karakter anlamını için yerel dil belirtimleri (yerel ayar kimlikleri) kullanır.  
  
 Yerel ayar kimliği değerleri tartışma için bkz [destekleyen birden çok dil](http://msdn.microsoft.com/en-us/47dc5add-232c-4268-b977-43e12da81ede).  
  
 Dize bir para birimi başarıyla dönüştürüldü değeri, bu değeri **COleCurrency** nesne ayarlanmış bu değeri ve durumuna geçerli.  
  
 Dize bir para birimi değeri dönüştürülemedi mı yoksa bu durum bir sayısal taşması olduysa **COleCurrency** nesnesi geçersiz.  
  
 Dize dönüştürme bellek ayırma hataları nedeniyle başarısız olursa, bu işlev oluşturur bir [CMemoryException](../../mfc/reference/cmemoryexception-class.md). Diğer hata durumu, bu işlev oluşturur bir [COleException](../../mfc/reference/coleexception-class.md).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCOleContainer#13](../../mfc/codesnippet/cpp/colecurrency-class_9.cpp)]  
  
##  <a name="colecurrency_relational_operators"></a>  COleCurrency ilişkisel işleçler  
 İki para birimi değerleri karşılaştırmak ve koşulun doğru olması durumunda sıfır olmayan döndürür; Aksi takdirde 0.  
  
```  
BOOL operator==(const COleCurrency& cur) const;  
BOOL operator!=(const COleCurrency& cur) const;  
BOOL operator<(const COleCurrency& cur) const;  
BOOL operator>(const COleCurrency& cur) const;  
BOOL operator<=(const COleCurrency& cur) const;  
BOOL operator>=(const COleCurrency& cur) const;  
```  
  
### <a name="remarks"></a>Açıklamalar  
  
> [!NOTE]
>  Sıralama işlemleri dönüş değerini ( **<**, **\< =**, **>**, **>=**) ya da işleneni durumu null veya geçersiz ise tanımlanmadı. Eşitlik işleçleri ( `==`, `!=`) işlenenleri durumunu göz önünde bulundurun.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCOleContainer#20](../../mfc/codesnippet/cpp/colecurrency-class_10.cpp)]  
  
##  <a name="setcurrency"></a>  COleCurrency::SetCurrency  
 Birimleri ve kesirli kısmı ayarlamak için bu üye işlevini çağırın **COleCurrency** nesnesi.  
  
```  
void SetCurrency(
    long nUnits,  
    long nFractionalUnits);
```  
  
### <a name="parameters"></a>Parametreler  
 `nUnits`, `nFractionalUnits`  
 Birimleri ve kesirli kısmını değeri (1/10, 000's)'daki bu kopyalanacak belirtmek **COleCurrency** nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Kesirli bölümü mutlak değerini 10. 000 ' büyükse, uygun düzeltme birimler, üçüncü aşağıdaki örneklerde gösterildiği gibi yapılır.  
  
 Birimleri ve kesirli bölümü tarafından imzalanan uzun değerler belirtilen unutmayın. Aşağıdaki örneklerde dördüncü parametreleri işaretleri farklı olduğunda ne olacağını gösterir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCOleContainer#14](../../mfc/codesnippet/cpp/colecurrency-class_11.cpp)]  
  
##  <a name="setstatus"></a>  COleCurrency::SetStatus  
 Bu durum (geçerlilik) ayarlamak için bu üye işlevini çağırın **COleCurrency** nesnesi.  
  
```  
void SetStatus(CurrencyStatus  status  );
```  
  
### <a name="parameters"></a>Parametreler  
 *Durumu*  
 Bu yeni durum **COleCurrency** nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 *Durum* tarafından tanımlanan parametre değeri `CurrencyStatus` numaralandırılmış içinde tanımlanan türü **COleCurrency** sınıfı.  
  
```  
enum CurrencyStatus {
    valid = 0,
    invalid = 1,
    null = 2
    };  
```  
  
 Bu durum değerleri kısa bir açıklaması için aşağıdaki listeye bakın:  
  
- **COleCurrency::valid** belirtir bu **COleCurrency** nesne geçerlidir.  
  
- **COleCurrency::invalid** belirtir bu **COleCurrency** nesnesi geçersiz; diğer bir deyişle, değeri yanlış olabilir.  
  
- **COleCurrency::null** belirtir bu **COleCurrency** nesnesi null, diğer bir deyişle, bu nesne için herhangi bir değer belirtildi. (Bu bir "herhangi bir değer aksine C++ kullanılmasının" veritabanı algılama "null" **NULL**.)  
  
    > [!CAUTION]
    >  Bu işlev, Gelişmiş programlama durumlar için kullanılır. Bu işlev, bu nesne verileri değiştirmez. Genellikle, boş veya geçersiz için durumunu ayarlamak için de kullanılır. Unutmayın atama işleci ( [işleç =](#operator_eq)) ve [SetCurrency](#setcurrency) kaynak değerler göre bir nesne durumunu ayarlayın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [COleVariant Sınıfı](../../mfc/reference/colevariant-class.md)
