---
title: CSettingsStore Sınıfı
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
ms.openlocfilehash: b1acf959c371aa23ac55ace7fea9466f0e20813f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318461"
---
# <a name="csettingsstore-class"></a>CSettingsStore Sınıfı

Windows API işlevlerini sarar ve kayıt defterine erişmek için kullandığınız nesne yönelimli bir arabirim sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CSettingsStore : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CSettingsStore::CSettingsStore](#csettingsstore)|Bir `CSettingsStore` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CSettingsStore::Kapat](#close)|Açık kayıt defteri anahtarını kapatır.|
|[CSettingsStore::CreateKey](#createkey)|Belirtilen anahtarı açar veya yoksa oluşturur.|
|[CSettingsStore::DeleteKey](#deletekey)|Belirtilen anahtarı ve tüm çocuklarını siler.|
|[CSettingsStore::DeleteValue](#deletevalue)|Açık anahtarın belirtilen değerini siler.|
|[CSettingsStore::Aç](#open)|Belirtilen anahtarı açar.|
|[CSettingsStore::Oku](#read)|Belirtilen anahtar değeri için verileri alır.|
|[CSettingsStore::Yaz](#write)|Açık anahtarın altında kayıt defterine bir değer yazar.|

## <a name="remarks"></a>Açıklamalar

Üye `CreateKey` işlevler `Open` ve çok benzer. Kayıt defteri anahtarı zaten `CreateKey` varsa `Open` ve aynı şekilde işlev. Ancak, kayıt defteri anahtarı yoksa, `CreateKey` bir hata `Open` değeri döndürür, ancak bu anahtar oluşturur.

## <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfın Aç ve Oku yöntemlerinin `CSettingsStore` nasıl kullanılacağını göstermektedir. Bu kod snippet [Araç İpucu Demo örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_ToolTipDemo#1](../../mfc/reference/codesnippet/cpp/csettingsstore-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

`CSettingsStore`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxsettingsstore.h

## <a name="csettingsstoreclose"></a><a name="close"></a>CSettingsStore::Kapat

Açık kayıt defteri anahtarını kapatır.

```
virtual void Close();
```

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bu yöntem [CSettingsStore Sınıfı'nın](../../mfc/reference/csettingsstore-class.md)yıkıcısından çağrılır.

## <a name="csettingsstorecreatekey"></a><a name="createkey"></a>CSettingsStore::CreateKey

Bir kayıt defteri anahtarını açar veya yoksa oluşturur.

```
virtual BOOL CreateKey(LPCTSTR pszPath);
```

### <a name="parameters"></a>Parametreler

*pszPath*<br/>
[içinde] Oluşturulacak veya açılacak anahtarın adını belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa 0; aksi takdirde sıfır olmayan bir değer.

### <a name="remarks"></a>Açıklamalar

`CreateKey`kayıt `m_hKey` defteri sorgularının kökü olarak kullanır. *PszPath'i* bir alt anahtar `m_hKey`olarak arar. Anahtar yoksa, `CreateKey` oluşturur. Aksi takdirde, anahtarı açar. `CreateKey`sonra `m_hKey` oluşturulan veya açılan tuşa ayarlar.

## <a name="csettingsstorecsettingsstore"></a><a name="csettingsstore"></a>CSettingsStore::CSettingsStore

Bir `CSettngsStore` nesnesi oluşturur.

```
CSettingsStore(
    BOOL bAdmin,
    BOOL bReadOnly);
```

### <a name="parameters"></a>Parametreler

*bYönetici*<br/>
[içinde] Nesnenin `CSettingsStore` yönetici modunda hareket edip etmediğini belirten boolean parametresi.

*bReadOnly*<br/>
[içinde] Nesnenin `CSettingsStore` salt okunur modunda oluşturulup oluşturulmadığını belirten boolean parametresi.

### <a name="remarks"></a>Açıklamalar

*bAdmin* TRUE olarak ayarlanırsa, `m_hKey` üye değişken **HKEY_LOCAL_MACHINE.** *bAdmin'i* FALSE olarak `m_hKey` ayarlarsanız, **HKEY_CURRENT_USER**olarak ayarlanır.

Güvenlik erişimi *bReadOnly* parametreye bağlıdır. *bReadonly* FALSE ise, güvenlik erişimi **KEY_ALL_ACCESS**olarak ayarlanır. *bReadyOnly* TRUE ise, güvenlik erişimi **KEY_QUERY_VALUE, KEY_NOTIFY** ve **KEY_ENUMERATE_SUB_KEYS**bir arada ayarlanır. Kayıt defteriyle birlikte güvenlik erişimi hakkında daha fazla bilgi için [Kayıt Defteri Anahtar Güvenliği ve Erişim Hakları'na](/windows/win32/SysInfo/registry-key-security-and-access-rights)bakın.

Sürümler `CSettingsStore` `m_hKey` için yıkıcı otomatik olarak.

## <a name="csettingsstoredeletekey"></a><a name="deletekey"></a>CSettingsStore::DeleteKey

Bir anahtarı ve tüm çocuklarını kayıt defterinden siler.

```
virtual BOOL DeleteKey(
    LPCTSTR pszPath,
    BOOL bAdmin = FALSE);
```

### <a name="parameters"></a>Parametreler

*pszPath*<br/>
[içinde] Silmek için anahtarın adı.

*bYönetici*<br/>
[içinde] Silmek için anahtarın konumunu belirten anahtar.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

`CSettingsStore` Nesne salt okunur modundaysa, bu yöntem başarısız olur.

*bAdmin* parametresi sıfırsa, `DeleteKey` **HKEY_CURRENT_USER**altında silmek için anahtar arar. *bAdmin* sıfır değilse, `DeleteKey` **HKEY_LOCAL_MACHINE**altında silmek için anahtar arar.

## <a name="csettingsstoredeletevalue"></a><a name="deletevalue"></a>CSettingsStore::DeleteValue

Bir değeri `m_hKey`siler.

```
virtual BOOL DeleteValue(LPCTSTR pszValue);
```

### <a name="parameters"></a>Parametreler

*pszValue*<br/>
[içinde] Kaldırılacak değer alanını belirtir.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

## <a name="csettingsstoreopen"></a><a name="open"></a>CSettingsStore::Aç

Kayıt defteri anahtarını açar.

```
virtual BOOL Open(LPCTSTR pszPath);
```

### <a name="parameters"></a>Parametreler

*pszPath*<br/>
[içinde] Kayıt defteri anahtarının adı.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu yöntem belirtilen anahtarı başarıyla açtıktan sonra, bu anahtarın koluna ayarlar. `m_hKey`

## <a name="csettingsstoreread"></a><a name="read"></a>CSettingsStore::Oku

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
[içinde] Kayıt defterinden okunacak değerin adını içeren null-sonlandırılan dize işaretçi.

*iVal*<br/>
[çıkış] Kayıt defteri anahtarından okunan değeri alan bir bir sonsayı değişkenine başvuru.

*dwVal*<br/>
[çıkış] Kayıt defteri anahtarından okunan değeri alan 32 bitlik çift sözcük değişkenine başvuru.

*sVal*<br/>
[çıkış] Kayıt defteri anahtarından okunan değeri alan bir dize değişkenine başvuru.

*scStringList*<br/>
[çıkış] Kayıt defteri anahtarından okunan değeri alan bir dize listesi değişkenine başvuru.

*scArray*<br/>
[çıkış] Kayıt defteri anahtarından okunan değeri alan bir dize dizisi değişkenine başvuru.

*dwcArray*<br/>
[çıkış] Kayıt defteri anahtarından okunan değeri alan 32 bitlik çift sözcük lütfit değişkenine başvuru.

*wcArray*<br/>
[çıkış] Kayıt defteri anahtarından okunan değeri alan 16 bitlik sözcük dizisi değişkenine başvuru.

*bcArray*<br/>
[çıkış] Kayıt defteri anahtarından okunan değeri alan bir bayt dizi değişkenine başvuru.

*lpPoint*<br/>
[çıkış] Kayıt defteri anahtarından `POINT` okunan değeri alan bir yapıya başvuru.

*Rect*<br/>
[çıkış] Kayıt defteri anahtarından okunan değeri alan bir [CRect](../../atl-mfc-shared/reference/crect-class.md) değişkenine başvuru.

*ppData*<br/>
[çıkış] Kayıt defteri anahtarından okunan değeri alan verilere işaretçi.

*pBayt*<br/>
[çıkış] İmzasız bir karşıcı değişkeni işaretçi. Bu *değişken, ppData* işaret arabellek boyutunu alır.

*list*<br/>
[çıkış] Kayıt defteri anahtarından okunan değeri alan bir [CObList](../../mfc/reference/coblist-class.md) değişkenine başvuru.

*obj*<br/>
[çıkış] Kayıt defteri anahtarından okunan değeri alan bir [CObject](../../mfc/reference/cobject-class.md) değişkenine başvuru.

*pObj*<br/>
[çıkış] Kayıt defteri anahtarından `CObject` okunan değeri alan bir değişkene başvuru.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

`Read`bir alt anahtar olarak *pszKey* için `m_hKey`denetler.

## <a name="csettingsstorewrite"></a><a name="write"></a>CSettingsStore::Yaz

Açık anahtarın altında kayıt defterine bir değer yazar.

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
[içinde] Ayarlayabilmek için değerin adını içeren bir dize işaretçisi.

*iVal*<br/>
[içinde] Depolamak için verileri içeren bir bir sonda değişkenine başvuru.

*dwVal*<br/>
[içinde] Depolamak için veri içeren 32 bit çift kelime değişkenine başvuru.

*pszVal*<br/>
[içinde] Depolamak için verileri içeren null-sonlandırılan dize değişkenini işaretçi.

*scStringList*<br/>
[içinde] Depolamak için veri içeren bir [CStringList](../../mfc/reference/cstringlist-class.md) değişkenine başvuru.

*bcArray*<br/>
[içinde] Depolamak için veri içeren bir bayt dizi değişkenine başvuru.

*scArray*<br/>
[içinde] Depolamak için veri içeren bir dize dizisi değişkenine başvuru.

*dwcArray*<br/>
[içinde] Depolamak için veri içeren 32 bit çift kelime dizi değişkenine başvuru.

*wcArray*<br/>
[içinde] Depolamak için veri içeren 16 bitlik bir sözcük dizisi değişkenine başvuru.

*Rect*<br/>
[içinde] Depolamak için veri içeren bir [CRect](../../atl-mfc-shared/reference/crect-class.md) değişkenine başvuru.

*lpPoint*<br/>
[içinde] Depolamak için veri `POINT` içeren bir değişken için bir işaretçi başvuru.

*Pdata*<br/>
[içinde] Depolamak için verileri içeren bir arabellek işaretçisi.

*nBayt*<br/>
[içinde] *pData* parametresinin işaret ettiği verilerin boyutlarını baytolarak belirtir.

*list*<br/>
[içinde] Depolamak için veri içeren bir [CObList](../../mfc/reference/coblist-class.md) değişkenine başvuru.

*obj*<br/>
[içinde] Depolamak için veri içeren bir [CObject](../../mfc/reference/cobject-class.md) değişkenine başvuru.

*pObj*<br/>
[içinde] Depolamak için verileri `CObject` içeren bir değişken için işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Doğru eğer başarılı; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Kayıt defterine yazmak için, bir [CSettingsStore](../../mfc/reference/csettingsstore-class.md) nesnesi oluştururken *bReadOnly* sıfır olmayan bir değer ayarlamanız gerekir. Daha fazla bilgi için [Bkz. CSettingsStore::CSettingsStore](#csettingsstore).

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CWinAppEx Sınıfı](../../mfc/reference/cwinappex-class.md)
