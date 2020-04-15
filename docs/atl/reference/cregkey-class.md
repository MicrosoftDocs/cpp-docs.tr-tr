---
title: CRegKey Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CRegKey
- ATLBASE/ATL::CRegKey
- ATLBASE/ATL::CRegKey::CRegKey
- ATLBASE/ATL::CRegKey::Attach
- ATLBASE/ATL::CRegKey::Close
- ATLBASE/ATL::CRegKey::Create
- ATLBASE/ATL::CRegKey::DeleteSubKey
- ATLBASE/ATL::CRegKey::DeleteValue
- ATLBASE/ATL::CRegKey::Detach
- ATLBASE/ATL::CRegKey::EnumKey
- ATLBASE/ATL::CRegKey::Flush
- ATLBASE/ATL::CRegKey::GetKeySecurity
- ATLBASE/ATL::CRegKey::NotifyChangeKeyValue
- ATLBASE/ATL::CRegKey::Open
- ATLBASE/ATL::CRegKey::QueryBinaryValue
- ATLBASE/ATL::CRegKey::QueryDWORDValue
- ATLBASE/ATL::CRegKey::QueryGUIDValue
- ATLBASE/ATL::CRegKey::QueryMultiStringValue
- ATLBASE/ATL::CRegKey::QueryQWORDValue
- ATLBASE/ATL::CRegKey::QueryStringValue
- ATLBASE/ATL::CRegKey::QueryValue
- ATLBASE/ATL::CRegKey::RecurseDeleteKey
- ATLBASE/ATL::CRegKey::SetBinaryValue
- ATLBASE/ATL::CRegKey::SetDWORDValue
- ATLBASE/ATL::CRegKey::SetGUIDValue
- ATLBASE/ATL::CRegKey::SetKeySecurity
- ATLBASE/ATL::CRegKey::SetKeyValue
- ATLBASE/ATL::CRegKey::SetMultiStringValue
- ATLBASE/ATL::CRegKey::SetQWORDValue
- ATLBASE/ATL::CRegKey::SetStringValue
- ATLBASE/ATL::CRegKey::SetValue
- ATLBASE/ATL::CRegKey::m_hKey
- ATLBASE/ATL::CRegKey::m_pTM
helpviewer_keywords:
- CRegKey class
- ATL, registry
- registry, deleting values
- registry, writing to
- registry, deleting keys
ms.assetid: 3afce82b-ba2c-4c1a-8404-dc969e1af74b
ms.openlocfilehash: 01810c16ff3e7fbc930983b9a52dc3a80f779f14
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81331041"
---
# <a name="cregkey-class"></a>CRegKey Sınıfı

Bu sınıf, sistem kayıt defterindeki girişleri işlemek için yöntemler sağlar.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
class CRegKey
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CregKey::CregKey](#cregkey)|Oluşturucu.|
|[CRegKey::~CRegKey](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CRegKey::Ekle](#attach)|M_hKey üye tutamacını ayarlayarak `CRegKey` nesneye [m_hKey](#m_hkey) bir HKEY `hKey`eklemek için bu yöntemi çağırın.|
|[CRegKey::Kapat](#close)|[m_hKey](#m_hkey) üye tutamacını serbest bırakmak ve NULL olarak ayarlamak için bu yöntemi arayın.|
|[CRegKey::Oluştur](#create)|'nin alt anahtarı yoksa, belirtilen anahtarı oluşturmak için bu `hKeyParent`yöntemi çağırın.|
|[CRegKey::DeleteSubKey](#deletesubkey)|Belirtilen anahtarı kayıt defterinden kaldırmak için bu yöntemi arayın.|
|[CRegKey::DeleteValue](#deletevalue)|Değer alanını [m_hKey](#m_hkey)kaldırmak için bu yöntemi arayın.|
|[CRegKey::Detach](#detach)|[M_hKey](#m_hkey) üye tutamacını `CRegKey` nesneden ayırmak ve NULL `m_hKey` olarak ayarlamak için bu yöntemi çağırın.|
|[CRegKey::EnumKey](#enumkey)|Açık kayıt defteri anahtarının alt anahtarlarını sayısallandırmak için bu yöntemi arayın.|
|[CRegKey::Flush](#flush)|Açık kayıt defteri anahtarının tüm özniteliklerini kayıt defterine yazmak için bu yöntemi arayın.|
|[CRegKey::GetKeySecurity](#getkeysecurity)|Açık kayıt defteri anahtarını koruyan güvenlik tanımlayıcısının bir kopyasını almak için bu yöntemi arayın.|
|[CRegKey::NotifyChangeKeyValue](#notifychangekeyvalue)|Bu yöntem, arayana açık kayıt defteri anahtarının özniteliklerinde veya içeriğinde yapılan değişiklikler hakkında bildirimde yer eder.|
|[CRegKey::Aç](#open)|Belirtilen anahtarı açmak ve bu anahtarın koluna [m_hKey](#m_hkey) ayarlamak için bu yöntemi arayın.|
|[CRegKey::QueryBinaryValue](#querybinaryvalue)|Belirli bir değer adı için ikili verileri almak için bu yöntemi çağırın.|
|[CRegKey::QueryDWORDValue](#querydwordvalue)|Belirli bir değer adı için DWORD verilerini almak için bu yöntemi çağırın.|
|[CRegKey::QueryGUIDValue](#queryguidvalue)|Belirtilen bir değer adı için GUID verilerini almak için bu yöntemi çağırın.|
|[CRegKey::QueryMultiStringValue](#querymultistringvalue)|Belirli bir değer adı için çok string verileri almak için bu yöntemi çağırın.|
|[CRegKey::QueryQWORDValue](#queryqwordvalue)|Belirli bir değer adı için QWORD verilerini almak için bu yöntemi arayın.|
|[CRegKey::QueryStringValue](#querystringvalue)|Belirli bir değer adı için dize verilerini almak için bu yöntemi çağırın.|
|[CRegKey::QueryValue](#queryvalue)|[m_hKey](#m_hkey)belirtilen değer alanı için verileri almak için bu yöntemi arayın. Bu yöntemin önceki sürümleri artık desteklenmez ve ATL_DEPRECATED olarak işaretlenir.|
|[CRegKey::RecurseDeleteKey](#recursedeletekey)|Belirtilen anahtarı kayıt defterinden kaldırmak ve alt anahtarları açıkça kaldırmak için bu yöntemi arayın.|
|[CRegKey::SetBinaryValue](#setbinaryvalue)|Kayıt defteri anahtarının ikili değerini ayarlamak için bu yöntemi arayın.|
|[CRegKey::SetDWORDValue](#setdwordvalue)|Kayıt defteri anahtarının DWORD değerini ayarlamak için bu yöntemi arayın.|
|[CRegKey::SetGUIDValue](#setguidvalue)|Kayıt defteri anahtarının GUID değerini ayarlamak için bu yöntemi arayın.|
|[CRegKey::SetKeySecurity](#setkeysecurity)|Kayıt defteri anahtarının güvenliğini ayarlamak için bu yöntemi arayın.|
|[CRegKey::SetKeyValue](#setkeyvalue)|Verileri belirtilen bir anahtarın belirli bir değer alanında depolamak için bu yöntemi çağırın.|
|[CregKey::SetMultiStringValue](#setmultistringvalue)|Kayıt defteri anahtarının çok string değerini ayarlamak için bu yöntemi çağırın.|
|[CRegKey::SetQWORDValue](#setqwordvalue)|Kayıt defteri anahtarının QWORD değerini ayarlamak için bu yöntemi arayın.|
|[CRegKey::SetStringValue](#setstringvalue)|Kayıt defteri anahtarının dize değerini ayarlamak için bu yöntemi çağırın.|
|[CRegKey::SetValue](#setvalue)|[Verileri m_hKey](#m_hkey)belirtilen değer alanında depolamak için bu yöntemi arayın. Bu yöntemin önceki sürümleri artık desteklenmez ve ATL_DEPRECATED olarak işaretlenir.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CRegKey::operatör HKEY](#operator_hkey)|Nesneyi `CRegKey` HKEY'e dönüştürür.|
|[CRegKey::operatör =](#operator_eq)|Atama işleci.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CRegKey::m_hKey](#m_hkey)|Nesneyle ilişkili kayıt defteri anahtarının `CRegKey` tutamacını içerir.|
|[CRegKey::m_pTM](#m_ptm)|Nesneye `CAtlTransactionManager` işaretçi|

## <a name="remarks"></a>Açıklamalar

`CRegKey`sistem kayıt defterinde anahtar lar ve değerler oluşturma ve silme yöntemleri sağlar. Kayıt defteri, yazılım sürüm numaraları, yüklü donanımın mantıksal-fiziksel eşlemeleri ve COM nesneleri gibi sistem bileşenleri için yüklemeye özgü bir tanım kümesi içerir.

`CRegKey`belirli bir makine için sistem kayıt defterine bir programlama arabirimi sağlar. Örneğin, belirli bir kayıt defteri anahtarını açmak için . `CRegKey::Open` Bir veri değerini almak veya `CRegKey::QueryValue` `CRegKey::SetValue`değiştirmek için sırasıyla arayın veya değiştirin. Bir anahtarı kapatmak `CRegKey::Close`için, arayın.

Bir anahtarı kapattığınızda, kayıt defteri verileri sabit diske yazılır (kızarılır). Bu işlem birkaç saniye sürebilir. Uygulamanızın kayıt defteri verilerini sabit diske açıkça yazması gerekiyorsa, [RegFlushKey](/windows/win32/api/winreg/nf-winreg-regflushkey) Win32 işlevini arayabilirsiniz. Ancak, `RegFlushKey` birçok sistem kaynakları kullanır ve yalnızca kesinlikle gerekli olduğunda çağrılmalıdır.

> [!IMPORTANT]
> Arayanın bir kayıt defteri konumu belirtmesine izin veren yöntemler, güvenilemeyen verileri okuma potansiyeline sahiptir. [RegQueryValueEx'i](/windows/win32/api/winreg/nf-winreg-regqueryvalueexw) kullanan yöntemler, bu işlevin NULL sonlandırılan dizeleri açıkça işlemediğini göz önünde bulundurmalıdır. Her iki koşul da arama kodu tarafından denetlenmelidir.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase.h

## <a name="cregkeyattach"></a><a name="attach"></a>CRegKey::Ekle

m_hKey [üye](#m_hkey) tutamacını *hKey'e*ayarlayarak `CRegKey` nesneye HKEY eklemek için bu yöntemi çağırın.

```
void Attach(HKEY hKey) throw();
```

### <a name="parameters"></a>Parametreler

*Hkey*<br/>
Kayıt defteri anahtarının tutamacı.

### <a name="remarks"></a>Açıklamalar

`Attach`null olmayan `m_hKey` ise ileri sürecektir.

## <a name="cregkeyclose"></a><a name="close"></a>CRegKey::Kapat

[m_hKey](#m_hkey) üye tutamacını serbest bırakmak ve NULL olarak ayarlamak için bu yöntemi arayın.

```
LONG Close() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, ERROR_SUCCESS döndürür; aksi takdirde bir hata değeri döndürür.

## <a name="cregkeycreate"></a><a name="create"></a>CRegKey::Oluştur

*hKeyParent*bir alt anahtar olarak yoksa, belirtilen anahtarı oluşturmak için bu yöntemi arayın.

```
LONG Create(
    HKEY hKeyParent,
    LPCTSTR lpszKeyName,
    LPTSTR lpszClass = REG_NONE,
    DWORD dwOptions = REG_OPTION_NON_VOLATILE,
    REGSAM samDesired = KEY_READ | KEY_WRITE,
    LPSECURITY_ATTRIBUTES lpSecAttr = NULL,
    LPDWORD lpdwDisposition = NULL) throw();
```

### <a name="parameters"></a>Parametreler

*hKeyParent*<br/>
Açık bir anahtarın sapı.

*lpszKeyName*<br/>
Oluşturulacak veya açılacak anahtarın adını belirtir. Bu ad *hKeyParent*bir alt anahtar olmalıdır.

*lpszClass*<br/>
Oluşturulacak veya açılacak anahtarın sınıfını belirtir. Varsayılan değer REG_NONE.

*Dwoptions*<br/>
Anahtar için seçenekler. Varsayılan değer REG_OPTION_NON_VOLATILE. Olası değerlerin ve açıklamaların listesi için Windows SDK'daki [RegCreateKeyEx](/windows/win32/api/winreg/nf-winreg-regcreatekeyexw) bölümüne bakın.

*samDesired*<br/>
Anahtarın güvenlik erişimi. Varsayılan değer KEY_READ &#124; KEY_WRITE. Olası değerlerin ve açıklamaların listesi `RegCreateKeyEx`için bkz.

*lpSecAttr*<br/>
Anahtarın tutamacının bir alt işlem tarafından devralınıp alınamayacağını gösteren [SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\)) bir yapıya işaretçi. Varsayılan olarak, bu parametre NULL 'dur (yani işbit devralınamaz).

*lpdwDisposition*<br/>
[çıkış] NULL yoksa, REG_CREATED_NEW_KEY (anahtar yoksa ve oluşturulduysa) veya REG_OPENED_EXISTING_KEY (anahtar varsa ve açılmışsa) alır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, ERROR_SUCCESS döndürür ve anahtarı açar. Yöntem başarısız olursa, iade değeri WINERROR'ta tanımlanan sıfır olmayan bir hata kodudur. H.

### <a name="remarks"></a>Açıklamalar

`Create`[m_hKey](#m_hkey) üyeyi bu anahtarın koluna ayarlar.

## <a name="cregkeycregkey"></a><a name="cregkey"></a>CregKey::CregKey

Oluşturucu.

```
CRegKey() throw();
CRegKey(CRegKey& key) throw();
explicit CRegKey(HKEY hKey) throw();
CRegKey(CAtlTransactionManager* pTM) throw();
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Bir `CRegKey` nesneye başvuru.

*Hkey*<br/>
Kayıt defteri anahtarının tutamacı.

*pTM*<br/>
CAtlTransactionManager nesnesine işaretçi

### <a name="remarks"></a>Açıklamalar

Yeni `CRegKey` bir nesne oluşturur. Nesne varolan `CRegKey` bir nesneden veya bir tanıtıcıdan bir kayıt defteri anahtarına oluşturulabilir.

## <a name="cregkeycregkey"></a><a name="dtor"></a>CRegKey::~CRegKey

Yıkıcı.

```
~CRegKey() throw();
```

### <a name="remarks"></a>Açıklamalar

Yıkıcı bültenleri `m_hKey`.

## <a name="cregkeydeletesubkey"></a><a name="deletesubkey"></a>CRegKey::DeleteSubKey

Belirtilen anahtarı kayıt defterinden kaldırmak için bu yöntemi arayın.

```
LONG DeleteSubKey(LPCTSTR lpszSubKey) throw();
```

### <a name="parameters"></a>Parametreler

*lpszSubKey*<br/>
Silmek için anahtarın adını belirtir. Bu ad [m_hKey](#m_hkey)bir alt anahtar olmalıdır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, ERROR_SUCCESS döndürür. Yöntem başarısız olursa, iade değeri WINERROR'ta tanımlanan sıfır olmayan bir hata kodudur. H.

### <a name="remarks"></a>Açıklamalar

`DeleteSubKey`yalnızca alt tuşu olmayan bir tuşu silebilir. Anahtarın alt tuşları varsa, bunun yerine [RecurseDeleteKey'i](#recursedeletekey) arayın.

## <a name="cregkeydeletevalue"></a><a name="deletevalue"></a>CRegKey::DeleteValue

Değer alanını [m_hKey](#m_hkey)kaldırmak için bu yöntemi arayın.

```
LONG DeleteValue(LPCTSTR lpszValue) throw();
```

### <a name="parameters"></a>Parametreler

*lpszValue*<br/>
Kaldırılacak değer alanını belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, ERROR_SUCCESS döndürür. Yöntem başarısız olursa, iade değeri WINERROR'ta tanımlanan sıfır olmayan bir hata kodudur. H.

## <a name="cregkeydetach"></a><a name="detach"></a>CRegKey::Detach

[M_hKey](#m_hkey) üye tutamacını `CRegKey` nesneden ayırmak ve NULL `m_hKey` olarak ayarlamak için bu yöntemi çağırın.

```
HKEY Detach() throw();
```

### <a name="return-value"></a>Dönüş Değeri

`CRegKey` Nesneyle ilişkili HKEY.

## <a name="cregkeyenumkey"></a><a name="enumkey"></a>CRegKey::EnumKey

Açık kayıt defteri anahtarının alt anahtarlarını sayısallandırmak için bu yöntemi arayın.

```
LONG EnumKey(
    DWORD iIndex,
    LPTSTR pszName,
    LPDWORD pnNameLength,
    FILETIME* pftLastWriteTime = NULL) throw();
```

### <a name="parameters"></a>Parametreler

*ıındex*<br/>
Alt anahtar dizini. Bu parametre ilk arama için sıfır olmalı ve sonraki aramalar için artımlı

*pszName*<br/>
Null karakterini sonlandırma dahil alt anahtarın adını alan bir arabellek işaretçisi. Yalnızca alt anahtarın adı tam anahtar hiyerarşisine değil arabelleğe kopyalanır.

*pnNameLength*<br/>
*PszName* parametresi tarafından belirtilen arabelleğe, TCHAR cinsinden boyutunu belirten bir değişkeni işaretçi. Bu boyut sonlandırıcı null karakteri içermelidir. Yöntem döndüğünde, *pnNameLength* tarafından işaret edilen değişken arabellekte depolanan karakter sayısını içerir. Döndürülen sayım sonlandırıcı null karakterini içermez.

*pftLastWriteTime*<br/>
Numaralandırılmış alt anahtarın en son yazıldığı zamanı alan bir değişkeni işaretle.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, iade değeri ERROR_SUCCESS. Yöntem başarısız olursa, iade değeri WINERROR'ta tanımlanan sıfır olmayan bir hata kodudur. H.

### <a name="remarks"></a>Açıklamalar

Alt anahtarları numaralandırmak için `CRegKey::EnumKey` sıfır diziniyle arayın. Dizin değerini artım ve yöntem ERROR_NO_MORE_ITEMS döndürene kadar yineleyin. Daha fazla bilgi için Windows SDK'daki [RegEnumKeyEx'e](/windows/win32/api/winreg/nf-winreg-regenumkeyexw) bakın.

## <a name="cregkeyflush"></a><a name="flush"></a>CRegKey::Flush

Açık kayıt defteri anahtarının tüm özniteliklerini kayıt defterine yazmak için bu yöntemi arayın.

```
LONG Flush() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, iade değeri ERROR_SUCCESS. Yöntem başarısız olursa, iade değeri WINERROR'ta tanımlanan sıfır olmayan bir hata kodudur. H.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için Windows SDK'daki [RegEnumFlush'a](/windows/win32/api/winreg/nf-winreg-regflushkey) bakın.

## <a name="cregkeygetkeysecurity"></a><a name="getkeysecurity"></a>CRegKey::GetKeySecurity

Açık kayıt defteri anahtarını koruyan güvenlik tanımlayıcısının bir kopyasını almak için bu yöntemi arayın.

```
LONG GetKeySecurity(
    SECURITY_INFORMATION si,
    PSECURITY_DESCRIPTOR psd,
    LPDWORD pnBytes) throw();
```

### <a name="parameters"></a>Parametreler

*Si*<br/>
İstenen güvenlik bilgilerini gösteren [SECURITY_INFORMATION](/windows/win32/SecAuthZ/security-information) değeri.

*Psd*<br/>
İstenen güvenlik tanımlayıcısının bir kopyasını alan arabellek işaretçisi.

*pnBayt*<br/>
Boyutu, bayt, arabellek *psd*tarafından işaret .

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, iade değeri ERROR_SUCCESS. Yöntem başarısız olursa, return value WINERROR'ta sıfır olmayan bir hata kodu tanımlanır. H.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [Bkz. RegGetKeySecurity.](/windows/win32/api/winreg/nf-winreg-reggetkeysecurity)

## <a name="cregkeym_hkey"></a><a name="m_hkey"></a>CRegKey::m_hKey

Nesneyle ilişkili kayıt defteri anahtarının `CRegKey` tutamacını içerir.

```
HKEY m_hKey;
```

## <a name="cregkeym_ptm"></a><a name="m_ptm"></a>CRegKey::m_pTM

Bir `CAtlTransactionManager` nesneye işaretçi.

```
CAtlTransactionManager* m_pTM;
```

### <a name="remarks"></a>Açıklamalar

## <a name="cregkeynotifychangekeyvalue"></a><a name="notifychangekeyvalue"></a>CRegKey::NotifyChangeKeyValue

Bu yöntem, arayana açık kayıt defteri anahtarının özniteliklerinde veya içeriğinde yapılan değişiklikler hakkında bildirimde yer eder.

```
LONG NotifyChangeKeyValue(
    BOOL bWatchSubtree,
    DWORD dwNotifyFilter,
    HANDLE hEvent,
    BOOL bAsync = TRUE) throw();
```

### <a name="parameters"></a>Parametreler

*bWatchSubtree*<br/>
Belirtilen anahtardaki ve tüm alt anahtarlarındaki veya yalnızca belirtilen anahtardaki değişiklikleri bildirecek bir bayrak belirtir. Bu parametre TRUE ise, yöntem anahtar ve alt tuşlarıdeğişiklikleri raporlar. Parametre FALSE ise, yöntem yalnızca anahtarda değişiklik bildirir.

*dwNotifyFilter*<br/>
Hangi değişikliklerin bildirilmesi gerektiğini denetleyen bir bayrak kümesi belirtir. Bu parametre aşağıdaki değerlerin bir birleşimi olabilir:

|Değer|Anlamı|
|-----------|-------------|
|REG_NOTIFY_CHANGE_NAME|Bir alt anahtar eklenirse veya silinirse arayanın bildirin.|
|REG_NOTIFY_CHANGE_ATTRIBUTES|Güvenlik tanımlayıcı bilgileri gibi anahtarın özniteliklerinde yapılan değişiklikleri arayanı bildirin.|
|REG_NOTIFY_CHANGE_LAST_SET|Anahtarın değerindeki değişiklikleri arayanı bildirin. Bu, bir değer eklemeyi veya silmeyi veya varolan bir değeri değiştirmeyi içerebilir.|
|REG_NOTIFY_CHANGE_SECURITY|Anahtarın güvenlik tanımlayıcısı değişiklikleri arayana bildirin.|

*hOlay*<br/>
Bir olayı ele alın. *bAsync* parametresi TRUE ise, yöntem hemen döner ve bu olay sinyal tarafından değişiklikler bildirilir. *bAsync* FALSE ise, *hEvent* yoksayılır.

*bAsync*<br/>
Yöntemraporlarının nasıl değiştiğini gösteren bir bayrak belirtir. Bu parametre TRUE ise, yöntem hemen döndürür ve belirtilen olayı işaretleyerek değişiklikleri bildirir. Bu parametre FALSE olduğunda, bir değişiklik gerçekleşene kadar yöntem geri dönmez. *hEvent* geçerli bir olay belirtmezse, *bAsync* parametresi DOĞRU olamaz.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, iade değeri ERROR_SUCCESS. Yöntem başarısız olursa, iade değeri WINERROR'ta tanımlanan sıfır olmayan bir hata kodudur. H.

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
> Belirtilen anahtar silinirse, bu yöntem arayanı bildirmez.

Daha fazla bilgi ve örnek bir program için [Bkz. RegNotifyChangeKeyValue](/windows/win32/api/winreg/nf-winreg-regnotifychangekeyvalue).

## <a name="cregkeyopen"></a><a name="open"></a>CRegKey::Aç

Belirtilen anahtarı açmak ve bu anahtarın koluna [m_hKey](#m_hkey) ayarlamak için bu yöntemi arayın.

```
LONG Open(
    HKEY hKeyParent,
    LPCTSTR lpszKeyName,
    REGSAM samDesired = KEY_READ | KEY_WRITE) throw();
```

### <a name="parameters"></a>Parametreler

*hKeyParent*<br/>
Açık bir anahtarın sapı.

*lpszKeyName*<br/>
Oluşturulacak veya açılacak anahtarın adını belirtir. Bu ad *hKeyParent*bir alt anahtar olmalıdır.

*samDesired*<br/>
Anahtarın güvenlik erişimi. Varsayılan değer KEY_ALL_ACCESS. Olası değerlerin ve açıklamaların listesi için Windows SDK'daki [RegCreateKeyEx](/windows/win32/api/winreg/nf-winreg-regcreatekeyexw) bölümüne bakın.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, ERROR_SUCCESS döndürür; aksi takdirde WINERROR'da tanımlanan sıfır olmayan bir hata değeri. H.

### <a name="remarks"></a>Açıklamalar

*lpszKeyName* parametresi NULL ise veya boş `Open` bir dize ye işaret ediyorsa, *hKeyParent*tarafından tanımlanan anahtarın yeni bir tutamacını açar, ancak daha önce açılmış herhangi bir tutamacı kapatmaz.

[CRegKey aksine::Create,](#create) `Open` yoksa belirtilen anahtarı oluşturmaz.

## <a name="cregkeyoperator-hkey"></a><a name="operator_hkey"></a>CRegKey::operatör HKEY

Nesneyi `CRegKey` HKEY'e dönüştürür.

```
operator HKEY() const throw();
```

## <a name="cregkeyoperator-"></a><a name="operator_eq"></a>CRegKey::operatör =

Atama işleci.

```
CRegKey& operator= (CRegKey& key) throw();
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Kopyalamanın anahtarı.

### <a name="return-value"></a>Dönüş Değeri

Yeni anahtara bir başvuru verir.

### <a name="remarks"></a>Açıklamalar

Bu işleç *anahtarı* geçerli nesnesinden ayırır ve `CRegKey` bunun yerine nesneye atar.

## <a name="cregkeyquerybinaryvalue"></a><a name="querybinaryvalue"></a>CRegKey::QueryBinaryValue

Belirli bir değer adı için ikili verileri almak için bu yöntemi çağırın.

```
LONG QueryBinaryValue(
    LPCTSTR pszValueName,
    void* pValue,
    ULONG* pnBytes) throw();
```

### <a name="parameters"></a>Parametreler

*pszValueName*<br/>
Sorgudeğeri adını içeren null-sonlandırılan dize işaretçi.

*pDeğer*<br/>
Değerin verilerini alan bir arabellek için işaretçi.

*pnBayt*<br/>
*PValue* parametresi tarafından işaret edilen arabelleğen baytlar halinde boyutunu belirten bir değişkeni işareteder. Yöntem döndüğünde, bu değişken arabelleğe kopyalanan verilerin boyutunu içerir.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, ERROR_SUCCESS döndürülür. Yöntem bir değeri okuyamazsa, WINERROR'ta tanımlanan sıfır olmayan bir hata kodu döndürür. H. Başvurulan veriler tür REG_BINARY değilse, ERROR_INVALID_DATA döndürülür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, `RegQueryValueEx` doğru veri türünün döndürüldürün kullanımını yapar ve onaylar. Daha fazla bilgi için [RegQueryValueEx'e](/windows/win32/api/winreg/nf-winreg-regqueryvalueexw) bakın.

> [!IMPORTANT]
> Bu yöntem, arayanın herhangi bir kayıt defteri konumunu belirtmesine ve güvenilemeyen verileri okumasına olanak tanır. Ayrıca, bu yöntem tarafından kullanılan [RegQueryValueEx](/windows/win32/api/winreg/nf-winreg-regqueryvalueexw) işlevi açıkça NULL sonlandırılan dizeleri işlemez. Her iki koşul da arama kodu tarafından denetlenmelidir.

## <a name="cregkeyquerydwordvalue"></a><a name="querydwordvalue"></a>CRegKey::QueryDWORDValue

Belirli bir değer adı için DWORD verilerini almak için bu yöntemi çağırın.

```
LONG QueryDWORDValue(
    LPCTSTR pszValueName,
    DWORD& dwValue) throw();
```

### <a name="parameters"></a>Parametreler

*pszValueName*<br/>
Sorgudeğeri adını içeren null-sonlandırılan dize işaretçi.

*dwDeğer*<br/>
DWORD alan bir arabellek için işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, ERROR_SUCCESS döndürülür. Yöntem bir değeri okuyamazsa, WINERROR'ta tanımlanan sıfır olmayan bir hata kodu döndürür. H. Başvurulan veriler tür REG_DWORD değilse, ERROR_INVALID_DATA döndürülür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, `RegQueryValueEx` doğru veri türünün döndürüldürün kullanımını yapar ve onaylar. Daha fazla bilgi için [RegQueryValueEx'e](/windows/win32/api/winreg/nf-winreg-regqueryvalueexw) bakın.

> [!IMPORTANT]
> Bu yöntem, arayanın herhangi bir kayıt defteri konumunu belirtmesine ve güvenilemeyen verileri okumasına olanak tanır. Ayrıca, bu yöntem tarafından kullanılan [RegQueryValueEx](/windows/win32/api/winreg/nf-winreg-regqueryvalueexw) işlevi açıkça NULL sonlandırılan dizeleri işlemez. Her iki koşul da arama kodu tarafından denetlenmelidir.

## <a name="cregkeyqueryguidvalue"></a><a name="queryguidvalue"></a>CRegKey::QueryGUIDValue

Belirtilen bir değer adı için GUID verilerini almak için bu yöntemi çağırın.

```
LONG QueryGUIDValue(
    LPCTSTR pszValueName,
    GUID& guidValue) throw();
```

### <a name="parameters"></a>Parametreler

*pszValueName*<br/>
Sorgudeğeri adını içeren null-sonlandırılan dize işaretçi.

*guidValue*<br/>
GUID alan bir değişkeni işaretle.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, ERROR_SUCCESS döndürülür. Yöntem bir değeri okuyamazsa, WINERROR'ta tanımlanan sıfır olmayan bir hata kodu döndürür. H. Başvurulan veriler geçerli bir GUID değilse, ERROR_INVALID_DATA döndürülür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, `CRegKey::QueryStringValue` [string'i CLSIDFromString](/windows/win32/api/combaseapi/nf-combaseapi-clsidfromstring)kullanarak bir GUID'den kullanır ve dönüştürür.

> [!IMPORTANT]
> Bu yöntem, arayanın herhangi bir kayıt defteri konumunu belirtmesine ve güvenilemeyen verileri okumasına olanak tanır.

## <a name="cregkeyquerymultistringvalue"></a><a name="querymultistringvalue"></a>CRegKey::QueryMultiStringValue

Belirli bir değer adı için çok string verileri almak için bu yöntemi çağırın.

```
LONG QueryMultiStringValue(
    LPCTSTR pszValueName,
    LPTSTR pszValue,
    ULONG* pnChars) throw();
```

### <a name="parameters"></a>Parametreler

*pszValueName*<br/>
Sorgudeğeri adını içeren null-sonlandırılan dize işaretçi.

*pszValue*<br/>
Çok dizeli verileri alan bir arabellek için işaretçi. Çok string, iki null karakter tarafından sonlandırılan bir dizi null-sonlandırılan dizedir.

*pnChars*<br/>
Boyutu, TCHARs, tampon *pszValue*tarafından işaret . Yöntem döndüğünde, *pnChars,* TCHARs, bir sonlandırıcı null karakter de dahil olmak üzere alınan multistring boyutunu içerir.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, ERROR_SUCCESS döndürülür. Yöntem bir değeri okuyamazsa, WINERROR'ta tanımlanan sıfır olmayan bir hata kodu döndürür. H. Başvurulan veriler tür REG_MULTI_SZ değilse, ERROR_INVALID_DATA döndürülür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, `RegQueryValueEx` doğru veri türünün döndürüldürün kullanımını yapar ve onaylar. Daha fazla bilgi için [RegQueryValueEx'e](/windows/win32/api/winreg/nf-winreg-regqueryvalueexw) bakın.

> [!IMPORTANT]
> Bu yöntem, arayanın herhangi bir kayıt defteri konumunu belirtmesine ve güvenilemeyen verileri okumasına olanak tanır. Ayrıca, bu yöntem tarafından kullanılan [RegQueryValueEx](/windows/win32/api/winreg/nf-winreg-regqueryvalueexw) işlevi açıkça NULL sonlandırılan dizeleri işlemez. Her iki koşul da arama kodu tarafından denetlenmelidir.

## <a name="cregkeyqueryqwordvalue"></a><a name="queryqwordvalue"></a>CRegKey::QueryQWORDValue

Belirli bir değer adı için QWORD verilerini almak için bu yöntemi arayın.

```
LONG QueryQWORDValue(
    LPCTSTR pszValueName,
    ULONGLONG& qwValue) throw();
```

### <a name="parameters"></a>Parametreler

*pszValueName*<br/>
Sorgudeğeri adını içeren null-sonlandırılan dize işaretçi.

*qwDeğer*<br/>
QWORD alan bir arabellek için işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, ERROR_SUCCESS döndürülür. Yöntem bir değeri okuyamazsa, WINERROR'ta tanımlanan sıfır olmayan bir hata kodu döndürür. H. Başvurulan veriler tür REG_QWORD değilse, ERROR_INVALID_DATA döndürülür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, `RegQueryValueEx` doğru veri türünün döndürüldürün kullanımını yapar ve onaylar. Daha fazla bilgi için [RegQueryValueEx'e](/windows/win32/api/winreg/nf-winreg-regqueryvalueexw) bakın.

> [!IMPORTANT]
> Bu yöntem, arayanın herhangi bir kayıt defteri konumunu belirtmesine ve güvenilemeyen verileri okumasına olanak tanır. Ayrıca, bu yöntem tarafından kullanılan [RegQueryValueEx](/windows/win32/api/winreg/nf-winreg-regqueryvalueexw) işlevi açıkça NULL sonlandırılan dizeleri işlemez. Her iki koşul da arama kodu tarafından denetlenmelidir.

## <a name="cregkeyquerystringvalue"></a><a name="querystringvalue"></a>CRegKey::QueryStringValue

Belirli bir değer adı için dize verilerini almak için bu yöntemi çağırın.

```
LONG QueryStringValue(
    LPCTSTR pszValueName,
    LPTSTR pszValue,
    ULONG* pnChars) throw();
```

### <a name="parameters"></a>Parametreler

*pszValueName*<br/>
Sorgudeğeri adını içeren null-sonlandırılan dize işaretçi.

*pszValue*<br/>
Dize verilerini alan bir arabellek için işaretçi.

*pnChars*<br/>
Boyutu, TCHARs, tampon *pszValue*tarafından işaret . Yöntem döndüğünde, *pnChars,* TCHARs, alınan dize boyutu, bir sonlandırıcı null karakter de dahil olmak üzere içerir.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, ERROR_SUCCESS döndürülür. Yöntem bir değeri okuyamazsa, WINERROR'ta tanımlanan sıfır olmayan bir hata kodu döndürür. H. Başvurulan veriler tür REG_SZ değilse, ERROR_INVALID_DATA döndürülür. Yöntem ERROR_MORE_DATA döndürürse, *pnChars* baytlar için gerekli arabellek boyutudeğil, sıfıra eşittir.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, `RegQueryValueEx` doğru veri türünün döndürüldürün kullanımını yapar ve onaylar. Daha fazla bilgi için [RegQueryValueEx'e](/windows/win32/api/winreg/nf-winreg-regqueryvalueexw) bakın.

> [!IMPORTANT]
> Bu yöntem, arayanın herhangi bir kayıt defteri konumunu belirtmesine ve güvenilemeyen verileri okumasına olanak tanır. Ayrıca, bu yöntem tarafından kullanılan [RegQueryValueEx](/windows/win32/api/winreg/nf-winreg-regqueryvalueexw) işlevi açıkça NULL sonlandırılan dizeleri işlemez. Her iki koşul da arama kodu tarafından denetlenmelidir.

## <a name="cregkeyqueryvalue"></a><a name="queryvalue"></a>CRegKey::QueryValue

[m_hKey](#m_hkey)belirtilen değer alanı için verileri almak için bu yöntemi arayın. Bu yöntemin önceki sürümleri artık desteklenmez ve ATL_DEPRECATED olarak işaretlenir.

```
LONG QueryValue(
    LPCTSTR pszValueName,
    DWORD* pdwType,
    void* pData,
    ULONG* pnBytes) throw();

ATL_DEPRECATED LONG QueryValue(
    DWORD& dwValue,
    LPCTSTR lpszValueName);

ATL_DEPRECATED LONG QueryValue(
    LPTSTR szValue,
    LPCTSTR lpszValueName,
    DWORD* pdwCount);
```

### <a name="parameters"></a>Parametreler

*pszValueName*<br/>
Sorgudeğeri adını içeren null-sonlandırılan dize işaretçi. *pszValueName* NULL veya boş bir dize ise, "", yöntem varsa anahtarın adsız veya varsayılan değeri için türü ve verileri alır.

*pdwType*<br/>
Belirtilen değerde depolanan veri türünü belirten bir kod alan bir değişkeni işaretçi. Tür kodu gerekli değilse *pdwType* parametresi NULL olabilir.

*Pdata*<br/>
Değerin verilerini alan bir arabellek için işaretçi. Veriler gerekli değilse, bu parametre NULL olabilir.

*pnBayt*<br/>
*PData* parametresi tarafından işaret edilen arabelleğebaytolarak boyutunu belirten bir değişkeni işareteder. Yöntem döndüğünde, bu değişken *pData'ya* kopyalanan verilerin boyutunu içerir.

*dwDeğer*<br/>
Değer alanının sayısal verileri.

*lpszValueName*<br/>
Sorgulanacak değer alanını belirtir.

*szDeğer*<br/>
Değer alanının dize verileri.

*pdwSayısı*<br/>
Dize verilerinin boyutu. Değeri başlangıçta *szValue* arabelleği boyutuna ayarlanır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, ERROR_SUCCESS döndürür; aksi takdirde, WINERROR'da tanımlanan sıfır olmayan bir hata kodu. H.

### <a name="remarks"></a>Açıklamalar

İki orijinal sürümü `QueryValue` artık desteklenmez ve ATL_DEPRECATED olarak işaretlenir. Derleyici, bu formlar kullanılırsa bir uyarı yayımlar.

Kalan yöntem RegQueryValueEx çağırır.

> [!IMPORTANT]
> Bu yöntem, arayanın herhangi bir kayıt defteri konumunu belirtmesine ve güvenilemeyen verileri okumasına olanak tanır. Ayrıca, bu yöntem tarafından kullanılan RegQueryValueEx işlevi açıkça NULL sonlandırılan dizeleri işlemez. Her iki koşul da arama kodu tarafından denetlenmelidir.

## <a name="cregkeyrecursedeletekey"></a><a name="recursedeletekey"></a>CRegKey::RecurseDeleteKey

Belirtilen anahtarı kayıt defterinden kaldırmak ve alt anahtarları açıkça kaldırmak için bu yöntemi arayın.

```
LONG RecurseDeleteKey(LPCTSTR lpszKey) throw();
```

### <a name="parameters"></a>Parametreler

*lpszKey*<br/>
Silmek için anahtarın adını belirtir. Bu ad [m_hKey](#m_hkey)bir alt anahtar olmalıdır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, ERROR_SUCCESS döndürür; aksi takdirde WINERROR'da tanımlanan sıfır olmayan bir hata değeri. H.

### <a name="remarks"></a>Açıklamalar

Anahtarın alt anahtarları varsa, anahtarı silmek için bu yöntemi aramanız gerekir.

## <a name="cregkeysetbinaryvalue"></a><a name="setbinaryvalue"></a>CRegKey::SetBinaryValue

Kayıt defteri anahtarının ikili değerini ayarlamak için bu yöntemi arayın.

```
LONG SetBinaryValue(
    LPCTSTR pszValueName,
    const void* pValue,
    ULONG nBytes) throw();
```

### <a name="parameters"></a>Parametreler

*pszValueName*<br/>
Ayarlanan değerin adını içeren bir dize işaretçisi. Bu ada sahip bir değer zaten yoksa, yöntem anahtara ekler.

*pDeğer*<br/>
Belirtilen değer adı ile depolanacak verileri içeren bir arabelleğe işaretçi.

*nBayt*<br/>
*pValue* parametresi tarafından işaret edilen bilgilerin boyutunu baytolarak belirtir.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, iade değeri ERROR_SUCCESS. Yöntem başarısız olursa, iade değeri WINERROR'ta tanımlanan sıfır olmayan bir hata kodudur. H.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, kayıt defterine değeri yazmak için [RegSetValueEx'i](/windows/win32/api/winreg/nf-winreg-regsetvalueexw) kullanır.

## <a name="cregkeysetdwordvalue"></a><a name="setdwordvalue"></a>CRegKey::SetDWORDValue

Kayıt defteri anahtarının DWORD değerini ayarlamak için bu yöntemi arayın.

```
LONG SetDWORDValue(LPCTSTR pszValueName, DWORD dwValue) throw();
```

### <a name="parameters"></a>Parametreler

*pszValueName*<br/>
Ayarlanan değerin adını içeren bir dize işaretçisi. Bu ada sahip bir değer zaten yoksa, yöntem anahtara ekler.

*dwDeğer*<br/>
Belirtilen değer adı ile depolanacak DWORD verileri.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, iade değeri ERROR_SUCCESS. Yöntem başarısız olursa, iade değeri WINERROR'ta tanımlanan sıfır olmayan bir hata kodudur. H.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, kayıt defterine değeri yazmak için [RegSetValueEx'i](/windows/win32/api/winreg/nf-winreg-regsetvalueexw) kullanır.

## <a name="cregkeysetguidvalue"></a><a name="setguidvalue"></a>CRegKey::SetGUIDValue

Kayıt defteri anahtarının GUID değerini ayarlamak için bu yöntemi arayın.

```
LONG SetGUIDValue(LPCTSTR pszValueName, REFGUID guidValue) throw();
```

### <a name="parameters"></a>Parametreler

*pszValueName*<br/>
Ayarlanan değerin adını içeren bir dize işaretçisi. Bu ada sahip bir değer zaten yoksa, yöntem anahtara ekler.

*guidValue*<br/>
Belirtilen değer adı ile depolanacak GUID başvurusu.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, iade değeri ERROR_SUCCESS. Yöntem başarısız olursa, iade değeri WINERROR'ta tanımlanan sıfır olmayan bir hata kodudur. H.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, `CRegKey::SetStringValue` [StringFromGUID2](/windows/win32/api/combaseapi/nf-combaseapi-stringfromguid2)kullanarak GUID'i kullanır ve bir dize dönüştürür.

## <a name="cregkeysetkeyvalue"></a><a name="setkeyvalue"></a>CRegKey::SetKeyValue

Verileri belirtilen bir anahtarın belirli bir değer alanında depolamak için bu yöntemi çağırın.

```
LONG SetKeyValue(
    LPCTSTR lpszKeyName,
    LPCTSTR lpszValue,
    LPCTSTR lpszValueName = NULL) throw();
```

### <a name="parameters"></a>Parametreler

*lpszKeyName*<br/>
Oluşturulacak veya açılacak anahtarın adını belirtir. Bu ad [m_hKey](#m_hkey)bir alt anahtar olmalıdır.

*lpszValue*<br/>
Depolanacak verileri belirtir. Bu parametre NULL olmayan olmalıdır.

*lpszValueName*<br/>
Ayarlanacak değer alanını belirtir. Bu ada sahip bir değer alanı anahtarda zaten yoksa, eklenir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, ERROR_SUCCESS döndürür; aksi takdirde, WINERROR'da tanımlanan sıfır olmayan bir hata kodu. H.

### <a name="remarks"></a>Açıklamalar

*lpszKeyName* anahtarını oluşturmak veya açmak ve *lpszValue* verilerini *lpszValueName* değer alanında depolamak için bu yöntemi arayın.

## <a name="cregkeysetkeysecurity"></a><a name="setkeysecurity"></a>CRegKey::SetKeySecurity

Kayıt defteri anahtarının güvenliğini ayarlamak için bu yöntemi arayın.

```
LONG SetKeySecurity(SECURITY_INFORMATION si, PSECURITY_DESCRIPTOR psd) throw();
```

### <a name="parameters"></a>Parametreler

*Si*<br/>
Ayarlamak için güvenlik tanımlayıcıbileşenleri belirtir. Değer aşağıdaki değerlerin bir birleşimi olabilir:

|Değer|Anlamı|
|-----------|-------------|
|DACL_SECURITY_INFORMATION|Anahtarın isteğe bağlı erişim kontrol listesini (DACL) ayarlar. Anahtar WRITE_DAC erişimi olmalıdır veya arama işlemi nesnenin sahibi olmalıdır.|
|GROUP_SECURITY_INFORMATION|Anahtarın birincil grup güvenlik tanımlayıcısını (SID) ayarlar. Anahtar WRITE_OWNER erişimi olmalıdır veya arama işlemi nesnenin sahibi olmalıdır.|
|OWNER_SECURITY_INFORMATION|Anahtarın sahibi SID'yi ayarlar. Anahtar WRITE_OWNER erişimi ne de arama işlemi nesnenin sahibi olmalıdır veya SE_TAKE_OWNERSHIP_NAME ayrıcalığı etkinleştirilmelidir.|
|SACL_SECURITY_INFORMATION|Anahtarın sistem erişim kontrol listesini (SACL) ayarlar. Anahtar alaerişimACCESS_SYSTEM_SECURITY olmalı. Bu erişimi elde etmenin en uygun yolu, arayanın geçerli erişim belirtecindeki SE_SECURITY_NAME [ayrıcalığını](/windows/win32/secauthz/privileges) etkinleştirmek, ACCESS_SYSTEM_SECURITY erişim için tutamacı açmak ve ayrıcalığı devre dışı etmektir.|

*Psd*<br/>
Belirtilen anahtar için ayarlanan güvenlik özniteliklerini belirten [bir SECURITY_DESCRIPTOR](/windows/win32/api/winnt/ns-winnt-security_descriptor) yapıişaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, iade değeri ERROR_SUCCESS. Yöntem başarısız olursa, iade değeri WINERROR'ta tanımlanan sıfır olmayan bir hata kodudur. H.

### <a name="remarks"></a>Açıklamalar

Anahtarın güvenlik özniteliklerini ayarlar. Daha fazla bilgi için [RegSetKeySecurity'ye](/windows/win32/api/winreg/nf-winreg-regsetkeysecurity) bakın.

## <a name="cregkeysetmultistringvalue"></a><a name="setmultistringvalue"></a>CregKey::SetMultiStringValue

Kayıt defteri anahtarının çok string değerini ayarlamak için bu yöntemi çağırın.

```
LONG SetMultiStringValue(LPCTSTR pszValueName, LPCTSTR pszValue) throw();
```

### <a name="parameters"></a>Parametreler

*pszValueName*<br/>
Ayarlanan değerin adını içeren bir dize işaretçisi. Bu ada sahip bir değer zaten yoksa, yöntem anahtara ekler.

*pszValue*<br/>
Belirtilen değer adı ile depolanacak multistring verileri işaretçi. Çok string, iki null karakter tarafından sonlandırılan bir dizi null-sonlandırılan dizedir.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, iade değeri ERROR_SUCCESS. Yöntem başarısız olursa, iade değeri WINERROR'ta tanımlanan sıfır olmayan bir hata kodudur. H.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, kayıt defterine değeri yazmak için [RegSetValueEx'i](/windows/win32/api/winreg/nf-winreg-regsetvalueexw) kullanır.

## <a name="cregkeysetqwordvalue"></a><a name="setqwordvalue"></a>CRegKey::SetQWORDValue

Kayıt defteri anahtarının QWORD değerini ayarlamak için bu yöntemi arayın.

```
LONG SetQWORDValue(LPCTSTR pszValueName, ULONGLONG qwValue) throw();
```

### <a name="parameters"></a>Parametreler

*pszValueName*<br/>
Ayarlanan değerin adını içeren bir dize işaretçisi. Bu ada sahip bir değer zaten yoksa, yöntem anahtara ekler.

*qwDeğer*<br/>
Belirtilen değer adı ile depolanacak QWORD verileri.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, iade değeri ERROR_SUCCESS. Yöntem başarısız olursa, iade değeri WINERROR'ta tanımlanan sıfır olmayan bir hata kodudur. H.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, kayıt defterine değeri yazmak için [RegSetValueEx'i](/windows/win32/api/winreg/nf-winreg-regsetvalueexw) kullanır.

## <a name="cregkeysetstringvalue"></a><a name="setstringvalue"></a>CRegKey::SetStringValue

Kayıt defteri anahtarının dize değerini ayarlamak için bu yöntemi çağırın.

```
LONG SetStringValue(
    LPCTSTR pszValueName,
    LPCTSTR pszValue,
    DWORD dwType = REG_SZ) throw();
```

### <a name="parameters"></a>Parametreler

*pszValueName*<br/>
Ayarlanan değerin adını içeren bir dize işaretçisi. Bu ada sahip bir değer zaten yoksa, yöntem anahtara ekler.

*pszValue*<br/>
Belirtilen değer adı ile depolanacak dize verilerini işaretçi.

*dwType*<br/>
Kayıt defterine yazılmak için dize türü: ya REG_SZ (varsayılan) veya REG_EXPAND_SZ (multistrings için).

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, iade değeri ERROR_SUCCESS. Yöntem başarısız olursa, iade değeri WINERROR'ta tanımlanan sıfır olmayan bir hata kodudur. H.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, kayıt defterine değeri yazmak için [RegSetValueEx'i](/windows/win32/api/winreg/nf-winreg-regsetvalueexw) kullanır.

## <a name="cregkeysetvalue"></a><a name="setvalue"></a>CRegKey::SetValue

[Verileri m_hKey](#m_hkey)belirtilen değer alanında depolamak için bu yöntemi arayın. Bu yöntemin önceki sürümleri artık desteklenmez ve ATL_DEPRECATED olarak işaretlenir.

```
LONG SetValue(
    LPCTSTR pszValueName,
    DWORD dwType,
    const void* pValue,
    ULONG nBytes) throw();

static LONG WINAPI SetValue(
    HKEY hKeyParent,
    LPCTSTR lpszKeyName,
    LPCTSTR lpszValue,
    LPCTSTR lpszValueName = NULL);

ATL_DEPRECATED LONG SetValue(
    DWORD dwValue,
    LPCTSTR lpszValueName);

ATL_DEPRECATED LONG SetValue(
    LPCTSTR lpszValue,
    LPCTSTR lpszValueName = NULL,
    bool bMulti = false,
    int nValueLen = -1);
```

### <a name="parameters"></a>Parametreler

*pszValueName*<br/>
Ayarlanan değerin adını içeren bir dize işaretçisi. Bu ada sahip bir değer anahtarda zaten yoksa, yöntem anahtara ekler. *pszValueName* NULL veya boş bir dize ise, "", yöntem anahtarın adsız veya varsayılan değeri için türü ve verileri ayarlar.

*dwType*<br/>
*pValue* parametresine göre işaret edilen veri türünü gösteren bir kod belirtir.

*pDeğer*<br/>
Belirtilen değer adı ile depolanacak verileri içeren bir arabelleğe işaretçi.

*nBayt*<br/>
*pValue* parametresi tarafından işaret edilen bilgilerin boyutunu baytolarak belirtir. Veriler REG_SZ, REG_EXPAND_SZ veya REG_MULTI_SZ türündeyse, *nByte'lar* sonlandırıcı null karakterin boyutunu içermelidir.

*hKeyParent*<br/>
Açık bir anahtarın sapı.

*lpszKeyName*<br/>
Oluşturulacak veya açılacak anahtarın adını belirtir. Bu ad *hKeyParent*bir alt anahtar olmalıdır.

*lpszValue*<br/>
Depolanacak verileri belirtir. Bu parametre NULL olmayan olmalıdır.

*lpszValueName*<br/>
Ayarlanacak değer alanını belirtir. Bu ada sahip bir değer alanı anahtarda zaten yoksa, eklenir.

*dwDeğer*<br/>
Depolanacak verileri belirtir.

*bMulti*<br/>
Yanlışsa, dize tipi REG_SZ olduğunu gösterir. Doğruysa, dize REG_MULTI_SZ türü multistring olduğunu gösterir.

*nValueLen*<br/>
*bMulti* doğruysa, *nValueLen* karakterlerdeki *lpszValue* dizesinin uzunluğudur. *bMulti* yanlışsa, -1 değeri yöntemin uzunluğu otomatik olarak hesapladığını gösterir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, ERROR_SUCCESS döndürür; aksi takdirde, WINERROR'da tanımlanan sıfır olmayan bir hata kodu. H.

### <a name="remarks"></a>Açıklamalar

İki orijinal sürümü `SetValue` ATL_DEPRECATED olarak işaretlenir ve artık kullanılmamalıdır. Derleyici, bu formlar kullanılırsa bir uyarı yayımlar.

Üçüncü yöntem [RegSetValueEx](/windows/win32/api/winreg/nf-winreg-regsetvalueexw)çağırır.

## <a name="see-also"></a>Ayrıca bkz.

[DCOM Örneği](../../overview/visual-cpp-samples.md)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
