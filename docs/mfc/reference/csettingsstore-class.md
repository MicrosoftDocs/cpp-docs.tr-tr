---
title: Csettingssstore sınıfı
ms.date: 11/04/2016
f1_keywords:
- CSettingsStore
- AFXSETTINGSSTORE/CSettingsStore
- AFXSETTINGSSTORE/CSettingsStore::CSettingsStore
- AFXSETTINGSSTORE/CSettingsStore::Close
- AFXSETTINGSSTORE/CSettingsStore::CreateKey
- AFXSETTINGSSTORE/CSettingsStore::DeleteKey
- AFXSETTINGSSTORE/CSettingsStore::DeleteValue
- AFXSETTINGSSTORE/CSettingsStore::Open
- AFXSETTINGSSTORE/CSettingsStore::Read
- AFXSETTINGSSTORE/CSettingsStore::Write
helpviewer_keywords:
- CSettingsStore [MFC], CSettingsStore
- CSettingsStore [MFC], Close
- CSettingsStore [MFC], CreateKey
- CSettingsStore [MFC], DeleteKey
- CSettingsStore [MFC], DeleteValue
- CSettingsStore [MFC], Open
- CSettingsStore [MFC], Read
- CSettingsStore [MFC], Write
ms.assetid: 0ea181de-a13e-4b29-b560-7c43838223ff
ms.openlocfilehash: 75d86b81d9651e5892913af5919ae0a78fe6bbc5
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69502916"
---
# <a name="csettingsstore-class"></a>Csettingssstore sınıfı

Windows API işlevlerini sarmalayan, kayıt defterine erişmek için kullandığınız nesne odaklı bir arabirim sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CSettingsStore : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Csettingssdeposu:: Csettingssdeposu](#csettingsstore)|Bir `CSettingsStore` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Csettingssstore:: Close](#close)|Açık kayıt defteri anahtarını kapatır.|
|[Csettingssstore:: CreateKey](#createkey)|Belirtilen anahtarı açar veya yoksa oluşturur.|
|[Csettingssdeposu::D eleteKey](#deletekey)|Belirtilen anahtarı ve tüm alt öğelerini siler.|
|[Csettingssdeposu::D eleteValue](#deletevalue)|Açık anahtarın belirtilen değerini siler.|
|[Csettingssstore:: Open](#open)|Belirtilen anahtarı açar.|
|[Csettingssdeposu:: Read](#read)|Belirtilen anahtar değeri için verileri alır.|
|[Csettingssdeposu:: Write](#write)|Açık anahtarın altındaki kayıt defterine bir değer yazar.|

## <a name="remarks"></a>Açıklamalar

Üye işlevleri `CreateKey` ve `Open` çok benzerdir. Kayıt defteri anahtarı zaten varsa `CreateKey` ve `Open` aynı şekilde çalışır. Ancak, kayıt defteri anahtarı yoksa, `CreateKey` bir hata değeri döndürecek `Open` şekilde onu oluşturacaktır.

## <a name="example"></a>Örnek

Aşağıdaki örnek, `CSettingsStore` sınıfının açık ve okuma yöntemlerinin nasıl kullanılacağını göstermektedir. Bu kod parçacığı, [araç Ipucu demo örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_ToolTipDemo#1](../../mfc/reference/codesnippet/cpp/csettingsstore-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CSettingsStore`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxsettingssfer. h

##  <a name="close"></a>Csettingssstore:: Close

Açık kayıt defteri anahtarını kapatır.

```
virtual void Close();
```

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bu yöntem [CSettingsStore sınıfının](../../mfc/reference/csettingsstore-class.md)yıkıcısında çağırılır.

##  <a name="createkey"></a>Csettingssstore:: CreateKey

Bir kayıt defteri anahtarı açar veya yoksa oluşturur.

```
virtual BOOL CreateKey(LPCTSTR pszPath);
```

### <a name="parameters"></a>Parametreler

*pszPath*<br/>
'ndaki Oluşturulacak veya açılacak bir anahtarın adını belirtir.

### <a name="return-value"></a>Dönüş Değeri

başarılı olursa 0; Aksi takdirde sıfır olmayan bir değer.

### <a name="remarks"></a>Açıklamalar

`CreateKey`, `m_hKey` kayıt defteri sorguları kökü olarak kullanır. *PszPath* öğesini öğesinin `m_hKey`bir alt anahtarı olarak arar. Anahtar yoksa, `CreateKey` oluşturur. Aksi takdirde, anahtarı açar. `CreateKey`sonra oluşturulan `m_hKey` veya açılan anahtar olarak ayarlar.

##  <a name="csettingsstore"></a>Csettingssdeposu:: Csettingssdeposu

Bir `CSettngsStore` nesnesi oluşturur.

```
CSettingsStore(
    BOOL bAdmin,
    BOOL bReadOnly);
```

### <a name="parameters"></a>Parametreler

*bAdmin*<br/>
'ndaki `CSettingsStore` Nesnenin yönetici modunda hareket edilip edilmeyeceğini belirten Boolean parametresi.

*bReadOnly*<br/>
'ndaki `CSettingsStore` Nesnenin salt okunurdur modunda oluşturulup oluşturulmayacağını belirten Boolean parametresi.

### <a name="remarks"></a>Açıklamalar

*BAdmin* true olarak ayarlanırsa, `m_hKey` üye değişkeni **HKEY_LOCAL_MACHINE**olarak ayarlanır. *BAdmin* değerini false olarak ayarlarsanız, `m_hKey` **HKEY_CURRENT_USER**olarak ayarlanır.

Güvenlik erişimi, *bReadOnly* parametresine bağlıdır. *BReadOnly* yanlış ise, güvenlik erişimi **KEY_ALL_ACCESS**olarak ayarlanır. *BReadyOnly* true ise, güvenlik erişimi **KEY_QUERY_VALUE, KEY_NOTIFY** ve **KEY_ENUMERATE_SUB_KEYS**birleşimine ayarlanır. Kayıt defteriyle birlikte güvenlik erişimi hakkında daha fazla bilgi için bkz. [kayıt defteri anahtarı güvenlik ve erişim hakları](/windows/win32/SysInfo/registry-key-security-and-access-rights).

`CSettingsStore` Yayınlar`m_hKey` için otomatik olarak yıkıcı.

##  <a name="deletekey"></a>Csettingssdeposu::D eleteKey

Bir anahtarı ve tüm alt öğelerini kayıt defterinden siler.

```
virtual BOOL DeleteKey(
    LPCTSTR pszPath,
    BOOL bAdmin = FALSE);
```

### <a name="parameters"></a>Parametreler

*pszPath*<br/>
'ndaki Silinecek anahtarın adı.

*bAdmin*<br/>
'ndaki Silinecek anahtarın konumunu belirten anahtar.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, `CSettingsStore` nesne salt okunurdur modunda olduğunda başarısız olur.

*BAdmin* parametresi sıfırsa, `DeleteKey` **HKEY_CURRENT_USER**altında silinecek anahtarı arar. *BAdmin* sıfır değilse, `DeleteKey` **HKEY_LOCAL_MACHINE**altında silinecek anahtarı arar.

##  <a name="deletevalue"></a>Csettingssdeposu::D eleteValue

Öğesinden `m_hKey`bir değer siler.

```
virtual BOOL DeleteValue(LPCTSTR pszValue);
```

### <a name="parameters"></a>Parametreler

*pszValue*<br/>
'ndaki Kaldırılacak değer alanını belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

##  <a name="open"></a>Csettingssstore:: Open

Bir kayıt defteri anahtarı açar.

```
virtual BOOL Open(LPCTSTR pszPath);
```

### <a name="parameters"></a>Parametreler

*pszPath*<br/>
'ndaki Kayıt defteri anahtarının adı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, belirtilen anahtarı başarıyla açtıktan sonra bu anahtarın tanıtıcısına `m_hKey` ayarlanır.

##  <a name="read"></a>Csettingssdeposu:: Read

Kayıt defterindeki bir anahtardan bir değer okur.

```
virtual BOOL Read(
    LPCTSTR pszKey,
    int& iVal);

virtual BOOL Read(
    LPCTSTR pszKey,
    DWORD& dwVal);

virtual BOOL Read(
    LPCTSTR pszKey,
    CString& sVal);

virtual BOOL Read(
    LPCTSTR pszKey,
    CStringList& scStringList);

virtual BOOL Read(
    LPCTSTR pszKey,
    CStringArray& scArray);

virtual BOOL Read(
    LPCTSTR pszKey,
    CDWordArray& dwcArray);

virtual BOOL Read(
    LPCTSTR pszKey,
    CWordArray& wcArray);

virtual BOOL Read(
    LPCTSTR pszKey,
    CByteArray& bcArray);

virtual BOOL Read(
    LPCTSTR pszKey,
    LPPOINT& lpPoint);

virtual BOOL Read(
    LPCTSTR pszKey,
    CRect& rect);

virtual BOOL Read(
    LPCTSTR pszKey,
    BYTE** ppData,
    UINT* pBytes);

virtual BOOL Read(
    LPCTSTR pszKey,
    CObList& list);

virtual BOOL Read(
    LPCTSTR pszKey,
    CObject& obj);

virtual BOOL Read(
    LPCTSTR pszKey,
    CObject*& pObj);
```

### <a name="parameters"></a>Parametreler

*pszKey*<br/>
'ndaki Kayıt defterinden okunacak değerin adını içeren, null ile sonlandırılmış bir dize işaretçisi.

*IVAL*<br/>
dışı Kayıt defteri anahtarından okunan değeri alan bir tamsayı değişkenine başvuru.

*dwVal*<br/>
dışı Kayıt defteri anahtarından okunan değeri alan 32 bitlik bir çift sözcük değişkenine başvuru.

*sVal*<br/>
dışı Kayıt defteri anahtarından okunan değeri alan bir dize değişkenine başvuru.

*scStringList*<br/>
dışı Kayıt defteri anahtarından okunan değeri alan bir dize listesi değişkenine başvuru.

*scArray*<br/>
dışı Kayıt defteri anahtarından okunan değeri alan bir dize dizisi değişkenine başvuru.

*dwcArray*<br/>
dışı Kayıt defteri anahtarından okunan değeri alan 32 bitlik bir çift sözcük dizisi değişkenine başvuru.

*wcArray*<br/>
dışı Kayıt defteri anahtarından okunan değeri alan 16 bitlik bir sözcük dizisi değişkenine başvuru.

*bcArray*<br/>
dışı Kayıt defteri anahtarından okunan değeri alan bir bayt dizisi değişkenine başvuru.

*Lppoınt*<br/>
dışı Kayıt defteri anahtarından okunan değeri alan `POINT` bir yapının işaretçisine başvuru.

*Rect*<br/>
dışı Kayıt defteri anahtarından okunan değeri alan bir [CRect](../../atl-mfc-shared/reference/crect-class.md) değişkenine başvuru.

*ppData*<br/>
dışı Kayıt defteri anahtarından okunan değeri alan verilerin işaretçisi işaretçisi.

*pBytes*<br/>
dışı İşaretsiz tamsayı değişkenine yönelik işaretçi. Bu değişken, *ppData* tarafından işaret edilen arabelleğin boyutunu alır.

*list*<br/>
dışı Kayıt defteri anahtarından okunan değeri alan bir [CObList](../../mfc/reference/coblist-class.md) değişkenine başvuru.

*obj*<br/>
dışı Kayıt defteri anahtarından okunan değeri alan bir [CObject](../../mfc/reference/cobject-class.md) değişkenine başvuru.

*pObj*<br/>
dışı Kayıt defteri anahtarından okunan değeri alan `CObject` bir değişkene yönelik bir işaretçiye başvuru.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

`Read`*pszKey* öğesini öğesinin `m_hKey`alt anahtarı olarak denetler.

##  <a name="write"></a>Csettingssdeposu:: Write

Açık anahtarın altındaki kayıt defterine bir değer yazar.

```
virtual BOOL Write(
    LPCTSTR pszKey,
    int iVal);

virtual BOOL Write(
    LPCTSTR pszKey,
    DWORD dwVal);

virtual BOOL Write(
    LPCTSTR pszKey,
    LPCTSTR pszVal);

virtual BOOL Write(
    LPCTSTR pszKey,
    CStringList& scStringList);

virtual BOOL Write(
    LPCTSTR pszKey,
    CByteArray& bcArray);

virtual BOOL Write(
    LPCTSTR pszKey,
    CStringArray& scArray);

virtual BOOL Write(
    LPCTSTR pszKey,
    CDWordArray& dwcArray);

virtual BOOL Write(
    LPCTSTR pszKey,
    CWordArray& wcArray);

virtual BOOL Write(
    LPCTSTR pszKey,
    const CRect& rect);

virtual BOOL Write(
    LPCTSTR pszKey,
    LPPOINT& lpPoint);

virtual BOOL Write(
    LPCTSTR pszKey,
    LPBYTE pData,
    UINT nBytes);

virtual BOOL Write(
    LPCTSTR pszKey,
    CObList& list);

virtual BOOL Write(
    LPCTSTR pszKey,
    CObject& obj);

virtual BOOL Write(
    LPCTSTR pszKey,
    CObject* pObj);
```

### <a name="parameters"></a>Parametreler

*pszKey*<br/>
'ndaki Ayarlanacak değerin adını içeren bir dize işaretçisi.

*IVAL*<br/>
'ndaki Depolanacak verileri içeren bir tamsayı değişkenine başvuru.

*dwVal*<br/>
'ndaki Depolanacak verileri içeren 32 bitlik bir çift sözcük değişkenine başvuru.

*pszVal*<br/>
'ndaki Depolanacak verileri içeren null ile sonlandırılmış bir dize değişkeni işaretçisi.

*scStringList*<br/>
'ndaki Depolanacak verileri içeren bir [CStringList](../../mfc/reference/cstringlist-class.md) değişkenine başvuru.

*bcArray*<br/>
'ndaki Depolanacak verileri içeren bir bayt dizisi değişkenine başvuru.

*scArray*<br/>
'ndaki Depolanacak verileri içeren bir dize dizisi değişkenine başvuru.

*dwcArray*<br/>
'ndaki Depolanacak verileri içeren 32 bitlik bir çift sözcük dizisi değişkenine başvuru.

*wcArray*<br/>
'ndaki Depolanacak verileri içeren 16 bit sözcük dizisi değişkenine başvuru.

*Rect*<br/>
'ndaki Depolanacak verileri içeren bir [CRect](../../atl-mfc-shared/reference/crect-class.md) değişkenine başvuru.

*Lppoınt*<br/>
'ndaki Depolanacak verileri içeren bir `POINT` değişkene yönelik bir işaretçiye başvuru.

*pData*<br/>
'ndaki Depolanacak verileri içeren bir arabelleğin işaretçisi.

*nBytes*<br/>
'ndaki *PData* parametresinin işaret ettiği verilerin boyutunu bayt cinsinden belirtir.

*list*<br/>
'ndaki Depolanacak verileri içeren bir [CObList](../../mfc/reference/coblist-class.md) değişkenine başvuru.

*obj*<br/>
'ndaki Depolanacak verileri içeren bir [CObject](../../mfc/reference/cobject-class.md) değişkenine başvuru.

*pObj*<br/>
'ndaki Depolanacak verileri içeren bir `CObject` değişken işaretçisi işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa doğru; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

Kayıt defterine yazmak için bir Csettingsherbunesnesi oluştururken *bReadOnly* değerini sıfır dışında bir değere ayarlamanız gerekir [](../../mfc/reference/csettingsstore-class.md) . Daha fazla bilgi için bkz. [Csettingssstore:: csettingssstore](#csettingsstore).

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CWinAppEx Sınıfı](../../mfc/reference/cwinappex-class.md)
