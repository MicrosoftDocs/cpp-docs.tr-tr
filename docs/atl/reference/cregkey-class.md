---
title: CRegKey sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- CRegKey class
- ATL, registry
- registry, deleting values
- registry, writing to
- registry, deleting keys
ms.assetid: 3afce82b-ba2c-4c1a-8404-dc969e1af74b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 75caf648b0c62827e9532fa3776def1a4e459a64
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43764016"
---
# <a name="cregkey-class"></a>CRegKey sınıfı

Bu sınıf girişleri sistem kayıt defterinde yönlendirmeye yönelik yöntemleri sağlar.

> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
class CRegKey
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CRegKey::CRegKey](#cregkey)|Oluşturucu.|
|[CRegKey:: ~ CRegKey](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CRegKey::Attach](#attach)|İçin bir HKEY eklemek için bu yöntemi çağırın `CRegKey` ayarlayarak nesne [m_hKey](#m_hkey) üye tanıtıcısını `hKey`.|
|[CRegKey::Close](#close)|Serbest bırakmak için bu yöntemi çağıran [m_hKey](#m_hkey) üye işlemek ve NULL olarak ayarlayın.|
|[CRegKey::Create](#create)|Bir alt yoksa, belirtilen anahtar oluşturmak için bu yöntemi çağırın `hKeyParent`.|
|[CRegKey::DeleteSubKey](#deletesubkey)|Belirtilen anahtarı kayıt defterinden kaldırmak için bu yöntemi çağırın.|
|[CRegKey::DeleteValue](#deletevalue)|Bir değer alanı kaldırmak için bu yöntemi çağırın [m_hKey](#m_hkey).|
|[CRegKey::Detach](#detach)|Ayırma için bu yöntemi çağırın [m_hKey](#m_hkey) üye tanıtıcıdan `CRegKey` ayarlayın ve nesne `m_hKey` null.|
|[CRegKey::EnumKey](#enumkey)|Kayıt defteri anahtarı alt anahtarları numaralandır için bu yöntemi çağırın.|
|[CRegKey::Flush](#flush)|Tüm kayıt defteri anahtarı öznitelikleri kayıt defterine yazmak için bu yöntemi çağırın.|
|[CRegKey::GetKeySecurity](#getkeysecurity)|Kayıt defteri anahtarı koruyan güvenlik tanımlayıcısı bir kopyasını almak için bu yöntemi çağırın.|
|[CRegKey::NotifyChangeKeyValue](#notifychangekeyvalue)|Bu yöntemi çağıran öznitelikleri veya kayıt defteri anahtarı içeriğini değişiklikleri hakkında bilgilendirir.|
|[CRegKey::Open](#open)|Belirtilen anahtarı'nı açın ve ayarlamak için bu yöntemi çağırın [m_hKey](#m_hkey) bu anahtarın işlenecek.|
|[CRegKey::QueryBinaryValue](#querybinaryvalue)|Belirtilen değer adı için ikili verileri almak için bu yöntemi çağırın.|
|[CRegKey::QueryDWORDValue](#querydwordvalue)|Belirtilen değer adı için DWORD verileri almak için bu yöntemi çağırın.|
|[CRegKey::QueryGUIDValue](#queryguidvalue)|Belirtilen değer adı için GUID verileri almak için bu yöntemi çağırın.|
|[CRegKey::QueryMultiStringValue](#querymultistringvalue)|Belirtilen değer adı için çok dizeli verileri almak için bu yöntemi çağırın.|
|[CRegKey::QueryQWORDValue](#queryqwordvalue)|Belirtilen değer adı için QWORD verileri almak için bu yöntemi çağırın.|
|[CRegKey::QueryStringValue](#querystringvalue)|Belirtilen değer adı için dize verileri almak için bu yöntemi çağırın.|
|[CRegKey::QueryValue](#queryvalue)|Belirtilen değer alanı için verileri almak için bu yöntemi çağırın [m_hKey](#m_hkey). Bu yöntemin önceki sürümleri artık desteklenmemektedir ve ATL_DEPRECATED işaretlenir.|
|[CRegKey::RecurseDeleteKey](#recursedeletekey)|Belirtilen anahtarı kayıt defterinden kaldırabilir ve tüm alt açıkça kaldırmak için bu yöntemi çağırın.|
|[CRegKey::SetBinaryValue](#setbinaryvalue)|İkili kayıt defteri anahtarı değerini ayarlamak için bu yöntemi çağırın.|
|[CRegKey::SetDWORDValue](#setdwordvalue)|Kayıt defteri anahtarı DWORD değerini ayarlamak için bu yöntemi çağırın.|
|[CRegKey::SetGUIDValue](#setguidvalue)|Kayıt defteri anahtarının GUID değeri ayarlamak için bu yöntemi çağırın.|
|[CRegKey::SetKeySecurity](#setkeysecurity)|Kayıt defteri anahtarının güvenliğini ayarlamak için bu yöntemi çağırın.|
|[CRegKey::SetKeyValue](#setkeyvalue)|Belirtilen anahtar belirtilen değer alanında verileri depolamak için bu yöntemi çağırın.|
|[CRegKey::SetMultiStringValue](#setmultistringvalue)|Kayıt defteri anahtarının çok dizeli değer ayarlamak için bu yöntemi çağırın.|
|[CRegKey::SetQWORDValue](#setqwordvalue)|QWORD kayıt defteri anahtarı değerini ayarlamak için bu yöntemi çağırın.|
|[CRegKey::SetStringValue](#setstringvalue)|Kayıt defteri anahtarının dize değerini ayarlamak için bu yöntemi çağırın.|
|[CRegKey::SetValue](#setvalue)|Belirtilen değer alanında verileri depolamak için bu yöntemi çağırın [m_hKey](#m_hkey). Bu yöntemin önceki sürümleri artık desteklenmemektedir ve ATL_DEPRECATED işaretlenir.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CRegKey::operator HKEY](#operator_hkey)|Dönüştürür bir `CRegKey` bir HKEY için nesne.|
|[CRegKey::operator =](#operator_eq)|Atama işleci.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CRegKey::m_hKey](#m_hkey)|İle ilişkili kayıt defteri anahtarının bir tanıtıcı içeren `CRegKey` nesne.|
|[CRegKey::m_pTM](#m_ptm)|İşaretçi `CAtlTransactionManager` nesnesi|

## <a name="remarks"></a>Açıklamalar

`CRegKey` anahtarları ve değerleri sistem kayıt defterinde oluşturma ve silme için yöntemler sağlar. Kayıt defteri bir yükleme özel yazılım sürüm numaraları, donanımla ve COM nesneleri fiziksel mantıksal eşleme gibi sistem bileşenleri için tanımları içerir.

`CRegKey` belirli bir makine için sistem kayıt defterine bir programlama arabirimi sağlar. Örneğin, belirli kayıt defteri anahtarını açmak için çağrı `CRegKey::Open`. Almak ya da bir veri değeri değiştirmek için çağrı `CRegKey::QueryValue` veya `CRegKey::SetValue`sırasıyla. Bir anahtar kapatmak için çağrı `CRegKey::Close`.

Bir anahtar kapattığınızda, kayıt defteri verilerini (boşaltılıyorsa) sabit diske yazılır. Bu işlem birkaç saniye sürebilir. Uygulamanızın açıkça kayıt defteri verisi sabit diske yazmanız gerekiyorsa çağırabilirsiniz [RegFlushKey](/windows/desktop/api/winreg/nf-winreg-regflushkey) Win32 işlevi. Ancak, `RegFlushKey` birçok sistem kaynaklarını kullanır ve yalnızca gerçekten gerekli olduğunda çağrılmalıdır.

> [!IMPORTANT]
>  Bir kayıt defteri konumu belirtmek çağrıyı yapanın herhangi bir yöntem, güvenilir olmayan verileri okumak için potansiyeline sahiptir. Olun yöntemleri kullanımını [RegQueryValueEx](/windows/desktop/api/winreg/nf-winreg-regqueryvalueexa) bu işlev, NULL sonlandırılan dize açıkça işlemez dikkate almalıdır. Her iki koşul için çağıran kod tarafından denetlenmelidir.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlbase.h

##  <a name="attach"></a>  CRegKey::Attach

İçin bir HKEY eklemek için bu yöntemi çağırın `CRegKey` ayarlayarak nesne [m_hKey](#m_hkey) üye tanıtıcısını *hKey*.

```
void Attach(HKEY hKey) throw();
```

### <a name="parameters"></a>Parametreler

*hKey*  
Bir kayıt defteri anahtarının tanıtıcısı.

### <a name="remarks"></a>Açıklamalar

`Attach` varsa onay `m_hKey` NULL değil.

##  <a name="close"></a>  CRegKey::Close

Serbest bırakmak için bu yöntemi çağıran [m_hKey](#m_hkey) üye işlemek ve NULL olarak ayarlayın.

```
LONG Close() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, ERROR_SUCCESS döndürür; Aksi takdirde bir hata değeri döndürür.

##  <a name="create"></a>  CRegKey::Create

Bir alt yoksa, belirtilen anahtar oluşturmak için bu yöntemi çağırın *hKeyParent*.

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

*hKeyParent*  
Açık bir anahtar tanıtıcısı.

*lpszKeyName*  
Oluşturulacak veya açılan bir anahtarın adını belirtir. Bu ad, bir alt olmalıdır *hKeyParent*.

*lpszClass*  
Açılan veya oluşturulacak anahtar sınıfını belirtir. REG_NONE varsayılan değerdir.

*dwOptions*  
Anahtar seçenekleri. REG_OPTION_NON_VOLATILE varsayılan değerdir. Olası değerler ve açıklamaları listesi için bkz. [RegCreateKeyEx](/windows/desktop/api/winreg/nf-winreg-regcreatekeyexa) Windows SDK.

*samDesired*  
Güvenlik erişim anahtarı. Varsayılan değer: KEY_READ &#124; KEY_WRITE. Olası değerler ve açıklamaları listesi için bkz. `RegCreateKeyEx`.

*lpSecAttr*  
Bir işaretçi bir [SECURITY_ATTRIBUTES](https://msdn.microsoft.com/library/windows/desktop/aa379560) tanıtıcı anahtarının bir alt işlem tarafından devralınıp alınmayacağını belirten yapısı. Varsayılan olarak, bu parametre NULL (tanıtıcı devralınamaz anlamına gelir) olur.

*lpdwDisposition*  
[out] (Anahtar vardı ve açıldı varsa) NULL olmayan, REG_CREATED_NEW_KEY (anahtar yoktu ve oluşturulan ise) ya da REG_OPENED_EXISTING_KEY alır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, ERROR_SUCCESS döndürür ve anahtarı'nı açar. Yöntem başarısız olursa, dönüş değeri WINERROR içinde tanımlanan bir sıfır olmayan hata kodudur. H

### <a name="remarks"></a>Açıklamalar

`Create` Ayarlar [m_hKey](#m_hkey) üye bu anahtarın işlenecek.

##  <a name="cregkey"></a>  CRegKey::CRegKey

Oluşturucu.

```
CRegKey() throw();
CRegKey(CRegKey& key) throw();
explicit CRegKey(HKEY hKey) throw();
CRegKey(CAtlTransactionManager* pTM) throw();
```

### <a name="parameters"></a>Parametreler

*Anahtarı*  
Bir başvuru bir `CRegKey` nesne.

*hKey*  
Bir kayıt defteri anahtarı için bir tanıtıcı.

*pTM*  
CAtlTransactionManager nesne işaretçisi

### <a name="remarks"></a>Açıklamalar

Yeni bir oluşturur `CRegKey` nesne. Varolan bir nesne oluşturulabilir `CRegKey` nesnesi veya bir kayıt defteri anahtarı için bir tanıtıcı.

##  <a name="dtor"></a>  CRegKey:: ~ CRegKey

Yıkıcı.

```
~CRegKey() throw();
```

### <a name="remarks"></a>Açıklamalar

Yıkıcı yayınlar `m_hKey`.

##  <a name="deletesubkey"></a>  CRegKey::DeleteSubKey

Belirtilen anahtarı kayıt defterinden kaldırmak için bu yöntemi çağırın.

```
LONG DeleteSubKey(LPCTSTR lpszSubKey) throw();
```

### <a name="parameters"></a>Parametreler

*lpszSubKey*  
Silinecek anahtar adını belirtir. Bu ad, bir alt olmalıdır [m_hKey](#m_hkey).

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, ERROR_SUCCESS döndürür. Yöntem başarısız olursa, dönüş değeri WINERROR içinde tanımlanan bir sıfır olmayan hata kodudur. H

### <a name="remarks"></a>Açıklamalar

`DeleteSubKey` yalnızca hiçbir alt anahtarları bir anahtar silebilirsiniz. Anahtarı alt anahtarları varsa, çağrı [RecurseDeleteKey](#recursedeletekey) yerine.

##  <a name="deletevalue"></a>  CRegKey::DeleteValue

Bir değer alanı kaldırmak için bu yöntemi çağırın [m_hKey](#m_hkey).

```
LONG DeleteValue(LPCTSTR lpszValue) throw();
```

### <a name="parameters"></a>Parametreler

*lpszValue*  
Kaldırmak için değer alanını belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, ERROR_SUCCESS döndürür. Yöntem başarısız olursa, dönüş değeri WINERROR içinde tanımlanan bir sıfır olmayan hata kodudur. H

##  <a name="detach"></a>  CRegKey::Detach

Ayırma için bu yöntemi çağırın [m_hKey](#m_hkey) üye tanıtıcıdan `CRegKey` ayarlayın ve nesne `m_hKey` null.

```
HKEY Detach() throw();
```

### <a name="return-value"></a>Dönüş Değeri

HKEY ilişkili `CRegKey` nesne.

##  <a name="enumkey"></a>  CRegKey::EnumKey

Kayıt defteri anahtarı alt anahtarları numaralandır için bu yöntemi çağırın.

```
LONG EnumKey(  
    DWORD iIndex,
    LPTSTR pszName,
    LPDWORD pnNameLength,
    FILETIME* pftLastWriteTime = NULL) throw();
```

### <a name="parameters"></a>Parametreler

*İIndex*  
Alt anahtar dizini. Bu parametre için ilk çağrı sıfır olmalıdır ve ardından sonraki çağrılar için artar

*pszName*  
Sondaki null karakter de dahil olmak üzere alt anahtar adı alan arabellek için işaretçi. Arabellek için tam anahtar hiyerarşisini değil yalnızca alt anahtar adı kopyalanır.

*pnNameLength*  
TCHARs, tarafından belirtilen arabellek boyutunu belirten bir değişken işaretçisi *pszName* parametresi. Bu boyutu sondaki null karakter içermelidir. Bu yöntem döndürdüğünde, işaret ettiği değişken *pnNameLength* arabellekteki depolanan karakterlerin sayısını içerir. Bu sayı, döndürülen sondaki boş karakter içermez.

*pftLastWriteTime*  
Zaman alan bir değişken işaretçisi numaralandırılmış alt son için yazılmıştır.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, döndürülen değer ERROR_SUCCESS olur. Yöntem başarısız olursa, dönüş değeri WINERROR içinde tanımlanan bir sıfır olmayan hata kodudur. H

### <a name="remarks"></a>Açıklamalar

Alt anahtarları numaralandır çağrısı `CRegKey::EnumKey` sıfır dizine sahip. Dizin değeri artırmak ve yöntem ERROR_NO_MORE_ITEMS dönene kadar tekrarlayın. Daha fazla bilgi için [RegEnumKeyEx](/windows/desktop/api/winreg/nf-winreg-regenumkeyexa) Windows SDK.

##  <a name="flush"></a>  CRegKey::Flush

Tüm kayıt defteri anahtarı öznitelikleri kayıt defterine yazmak için bu yöntemi çağırın.

```
LONG Flush() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, döndürülen değer ERROR_SUCCESS olur. Yöntem başarısız olursa, dönüş değeri WINERROR içinde tanımlanan bir sıfır olmayan hata kodudur. H

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [RegEnumFlush](/windows/desktop/api/winreg/nf-winreg-regflushkey) Windows SDK.

##  <a name="getkeysecurity"></a>  CRegKey::GetKeySecurity

Kayıt defteri anahtarı koruyan güvenlik tanımlayıcısı bir kopyasını almak için bu yöntemi çağırın.

```
LONG GetKeySecurity(  
    SECURITY_INFORMATION si,
    PSECURITY_DESCRIPTOR psd,
    LPDWORD pnBytes) throw();
```

### <a name="parameters"></a>Parametreler

*sı*  
[SECURITY_INFORMATION](/windows/desktop/SecAuthZ/security-information) istenen güvenlik bilgilerini belirten değer.

*PSD*  
İstenen güvenlik tanımlayıcısı bir kopyasını alan arabellek için işaretçi.

*pnBytes*  
İşaret ettiği arabelleğin bayt cinsinden boyutu *psd*.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, döndürülen değer ERROR_SUCCESS olur. Yöntem başarısız olursa, dönüş WINERROR içinde tanımlanan sıfır olmayan hata kodu değeridir. H

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [RegGetKeySecurity](/windows/desktop/api/winreg/nf-winreg-reggetkeysecurity).

##  <a name="m_hkey"></a>  CRegKey::m_hKey

İle ilişkili kayıt defteri anahtarının bir tanıtıcı içeren `CRegKey` nesne.

```
HKEY m_hKey;
```

##  <a name="m_ptm"></a>  CRegKey::m_pTM

İşaretçi bir `CAtlTransactionManager` nesne.

```
CAtlTransactionManager* m_pTM;
```

### <a name="remarks"></a>Açıklamalar

##  <a name="notifychangekeyvalue"></a>  CRegKey::NotifyChangeKeyValue

Bu yöntemi çağıran öznitelikleri veya kayıt defteri anahtarı içeriğini değişiklikleri hakkında bilgilendirir.

```
LONG NotifyChangeKeyValue(  
    BOOL bWatchSubtree,
    DWORD dwNotifyFilter,
    HANDLE hEvent,
    BOOL bAsync = TRUE) throw();
```

### <a name="parameters"></a>Parametreler

*bWatchSubtree*  
Belirtilen anahtarı ve tüm alt anahtarlarını veya yalnızca belirtilen anahtarı değişiklikleri rapor gösteren bir bayrak belirtir. Bu parametre TRUE ise, yöntem anahtarında ve onun alt değişiklikleri bildirir. Bu parametre FALSE ise, yöntemi yalnızca anahtar değişiklik bildirir.

*dwNotifyFilter*  
Hangi değişiklikleri denetleyen bayrak kümesi bildirileceğini belirtir. Bu parametre aşağıdaki değerleri birleşimi olabilir:

|Değer|Açıklama|
|-----------|-------------|
|REG_NOTIFY_CHANGE_NAME|Bir alt eklediyseniz veya çağıranın bildirin.|
|REG_NOTIFY_CHANGE_ATTRIBUTES|Güvenlik açıklayıcı bilgisi gibi anahtar özniteliklerini değişiklikleri çağıran bildirin.|
|REG_NOTIFY_CHANGE_LAST_SET|Anahtar değerini değişiklikleri çağıran bildirin. Bu, ekleme veya silme bir değer ya da var olan bir değer değiştirme içerebilir.|
|REG_NOTIFY_CHANGE_SECURITY|Güvenlik tanımlayıcısı anahtarının değişiklikleri çağıran bildirin.|

*hEvent*  
Bir olay tanıtıcısı olarak ekleyin. Varsa *bAsync* parametre TRUE ise yöntem hemen döner ve değişiklikler, bu olayın sinyal tarafından raporlanır. Varsa *bAsync* false değerine *hEvent* göz ardı edilir.

*bAsync*  
Yöntem değişiklikleri nasıl raporları gösteren bir bayrak belirtir. Bu parametre TRUE ise, yöntem hemen döner ve belirtilen olaya sinyal tarafından değişiklikler raporlar. Bu parametre FALSE olduğunda, bir değişiklik meydana gelene kadar yöntemi döndürmez. Varsa *hEvent* geçerli bir olay belirtmiyor *bAsync* parametresi TRUE olamaz.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, döndürülen değer ERROR_SUCCESS olur. Yöntem başarısız olursa, dönüş değeri WINERROR içinde tanımlanan bir sıfır olmayan hata kodudur. H

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
>  Belirtilen anahtarı silinirse bu yöntemi çağıran bilgilendirmez.

Daha fazla bilgi ve örnek programı için bkz. [RegNotifyChangeKeyValue](/windows/desktop/api/winreg/nf-winreg-regnotifychangekeyvalue).

##  <a name="open"></a>  CRegKey::Open

Belirtilen anahtarı'nı açın ve ayarlamak için bu yöntemi çağırın [m_hKey](#m_hkey) bu anahtarın işlenecek.

```
LONG Open(  
    HKEY hKeyParent,
    LPCTSTR lpszKeyName,
    REGSAM samDesired = KEY_READ | KEY_WRITE) throw();
```

### <a name="parameters"></a>Parametreler

*hKeyParent*  
Açık bir anahtar tanıtıcısı.

*lpszKeyName*  
Oluşturulacak veya açılan bir anahtarın adını belirtir. Bu ad, bir alt olmalıdır *hKeyParent*.

*samDesired*  
Güvenlik erişim anahtarı. KEY_ALL_ACCESS varsayılan değerdir. Olası değerler ve açıklamaları listesi için bkz. [RegCreateKeyEx](/windows/desktop/api/winreg/nf-winreg-regcreatekeyexa) Windows SDK.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, ERROR_SUCCESS döndürür; Aksi takdirde, sıfır olmayan hata değeri WINERROR içinde tanımlanır. H

### <a name="remarks"></a>Açıklamalar

Varsa *lpszKeyName* parametredir NULL veya noktaları boş bir dize `Open` tarafından tanımlanan anahtarın yeni bir tanıtıcı açılır *hKeyParent*, ancak herhangi bir önceden açılmış tutamacı kapatmaz.

Farklı [CRegKey::Create](#create), `Open` belirtilen anahtar mevcut değilse oluşturulmaz.

##  <a name="operator_hkey"></a>  CRegKey::operator HKEY

Dönüştürür bir `CRegKey` bir HKEY için nesne.

```  
operator HKEY() const throw();
```

##  <a name="operator_eq"></a>  CRegKey::operator =

Atama işleci.

```
CRegKey& operator= (CRegKey& key) throw();
```

### <a name="parameters"></a>Parametreler

*Anahtarı*  
Kopyalamak için anahtar.

### <a name="return-value"></a>Dönüş Değeri

Yeni anahtar için bir başvuru döndürür.

### <a name="remarks"></a>Açıklamalar

Bu işleç ayırır *anahtarı* kendi geçerli nesneden ve buna atayan `CRegKey` bunun yerine nesne.

##  <a name="querybinaryvalue"></a>  CRegKey::QueryBinaryValue

Belirtilen değer adı için ikili verileri almak için bu yöntemi çağırın.

```
LONG QueryBinaryValue(  
    LPCTSTR pszValueName,
    void* pValue,
    ULONG* pnBytes) throw();
```

### <a name="parameters"></a>Parametreler

*pszValueName*  
Sorgu için değerin adını içeren null ile sonlandırılmış bir dize işaretçisi.

*pValue*  
Değer verisini alan arabellek için işaretçi.

*pnBytes*  
Arabelleğin bayt cinsinden boyutunu belirten bir değişken işaretçisi tarafından işaret edilen *pValue* parametresi. Yöntem döndürüldüğünde, bu değişken arabelleğe kopyalanan verilerin boyutunu içerir.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa ERROR_SUCCESS döndürülür. Bir değer okumak yöntem başarısız olursa WINERROR içinde tanımlanan bir sıfır olmayan hata kodu döndürür. H Başvurulan veri türü REG_BINARY değil, ERROR_INVALID_DATA döndürülür.

### <a name="remarks"></a>Açıklamalar

Bu yöntemi kullanır `RegQueryValueEx` ve doğru veri türünü verdiğini onaylar. Bkz: [RegQueryValueEx](/windows/desktop/api/winreg/nf-winreg-regqueryvalueexa) daha fazla ayrıntı için.

> [!IMPORTANT]
>  Bu yöntem, güvenilir olmayan verileri okunurken, herhangi bir kayıt defteri konumu belirtmek çağıranın sağlar. Ayrıca, [RegQueryValueEx](/windows/desktop/api/winreg/nf-winreg-regqueryvalueexa) bu yöntem tarafından kullanılan işlevi, NULL sonlandırılan dize açıkça işlemez. Her iki koşul için çağıran kod tarafından denetlenmelidir.

##  <a name="querydwordvalue"></a>  CRegKey::QueryDWORDValue

Belirtilen değer adı için DWORD verileri almak için bu yöntemi çağırın.

```
LONG QueryDWORDValue(  
    LPCTSTR pszValueName,
    DWORD& dwValue) throw();
```

### <a name="parameters"></a>Parametreler

*pszValueName*  
Sorgu için değerin adını içeren null ile sonlandırılmış bir dize işaretçisi.

*dwValue*  
DWORD alan arabellek için işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa ERROR_SUCCESS döndürülür. Bir değer okumak yöntem başarısız olursa WINERROR içinde tanımlanan bir sıfır olmayan hata kodu döndürür. H Başvurulan veri türü REG_DWORD değil, ERROR_INVALID_DATA döndürülür.

### <a name="remarks"></a>Açıklamalar

Bu yöntemi kullanır `RegQueryValueEx` ve doğru veri türünü verdiğini onaylar. Bkz: [RegQueryValueEx](/windows/desktop/api/winreg/nf-winreg-regqueryvalueexa) daha fazla ayrıntı için.

> [!IMPORTANT]
>  Bu yöntem, güvenilir olmayan verileri okunurken, herhangi bir kayıt defteri konumu belirtmek çağıranın sağlar. Ayrıca, [RegQueryValueEx](/windows/desktop/api/winreg/nf-winreg-regqueryvalueexa) bu yöntem tarafından kullanılan işlevi, NULL sonlandırılan dize açıkça işlemez. Her iki koşul için çağıran kod tarafından denetlenmelidir.

##  <a name="queryguidvalue"></a>  CRegKey::QueryGUIDValue

Belirtilen değer adı için GUID verileri almak için bu yöntemi çağırın.

```
LONG QueryGUIDValue(  
    LPCTSTR pszValueName,
    GUID& guidValue) throw();
```

### <a name="parameters"></a>Parametreler

*pszValueName*  
Sorgu için değerin adını içeren null ile sonlandırılmış bir dize işaretçisi.

*guidValue*  
GUID alan bir değişken işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa ERROR_SUCCESS döndürülür. Bir değer okumak yöntem başarısız olursa WINERROR içinde tanımlanan bir sıfır olmayan hata kodu döndürür. H Başvurulan veriler geçerli bir GUID değil, ERROR_INVALID_DATA döndürülür.

### <a name="remarks"></a>Açıklamalar

Bu yöntemi kullanır `CRegKey::QueryStringValue` ve kullanarak bir GUID dizesi dönüştürür [CLSIDFromString](/windows/desktop/api/combaseapi/nf-combaseapi-clsidfromstring).

> [!IMPORTANT]
>  Bu yöntem, güvenilir olmayan verileri okunurken, herhangi bir kayıt defteri konumu belirtmek çağıranın sağlar.

##  <a name="querymultistringvalue"></a>  CRegKey::QueryMultiStringValue

Belirtilen değer adı için çok dizeli verileri almak için bu yöntemi çağırın.

```
LONG QueryMultiStringValue(  
    LPCTSTR pszValueName,
    LPTSTR pszValue,
    ULONG* pnChars) throw();
```

### <a name="parameters"></a>Parametreler

*pszValueName*  
Sorgu için değerin adını içeren null ile sonlandırılmış bir dize işaretçisi.

*pszValue*  
Çok dizeli verileri alan bir arabellek için işaretçi. Bir multistring iki null karakter ile sona erdi, null ile sonlandırılmış dizeler dizisidir.

*pnChars*  
TCHARs, işaret ettiği arabellek büyüklüğü *pszValue*. Yöntem döndürüldüğünde *pnChars* multistring alındığında, bir sonlandırıcı null karakter de dahil olmak üzere, bir TCHARs boyutunu içerir.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa ERROR_SUCCESS döndürülür. Bir değer okumak yöntem başarısız olursa WINERROR içinde tanımlanan bir sıfır olmayan hata kodu döndürür. H Başvurulan veri türü REG_MULTI_SZ değil, ERROR_INVALID_DATA döndürülür.

### <a name="remarks"></a>Açıklamalar

Bu yöntemi kullanır `RegQueryValueEx` ve doğru veri türünü verdiğini onaylar. Bkz: [RegQueryValueEx](/windows/desktop/api/winreg/nf-winreg-regqueryvalueexa) daha fazla ayrıntı için.

> [!IMPORTANT]
>  Bu yöntem, güvenilir olmayan verileri okunurken, herhangi bir kayıt defteri konumu belirtmek çağıranın sağlar. Ayrıca, [RegQueryValueEx](/windows/desktop/api/winreg/nf-winreg-regqueryvalueexa) bu yöntem tarafından kullanılan işlevi, NULL sonlandırılan dize açıkça işlemez. Her iki koşul için çağıran kod tarafından denetlenmelidir.

##  <a name="queryqwordvalue"></a>  CRegKey::QueryQWORDValue

Belirtilen değer adı için QWORD verileri almak için bu yöntemi çağırın.

```
LONG QueryQWORDValue(  
    LPCTSTR pszValueName,
    ULONGLONG& qwValue) throw();
```

### <a name="parameters"></a>Parametreler

*pszValueName*  
Sorgu için değerin adını içeren null ile sonlandırılmış bir dize işaretçisi.

*qwValue*  
QWORD alan arabellek için işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa ERROR_SUCCESS döndürülür. Bir değer okumak yöntem başarısız olursa WINERROR içinde tanımlanan bir sıfır olmayan hata kodu döndürür. H Başvurulan veri türü REG_QWORD değil, ERROR_INVALID_DATA döndürülür.

### <a name="remarks"></a>Açıklamalar

Bu yöntemi kullanır `RegQueryValueEx` ve doğru veri türünü verdiğini onaylar. Bkz: [RegQueryValueEx](/windows/desktop/api/winreg/nf-winreg-regqueryvalueexa) daha fazla ayrıntı için.

> [!IMPORTANT]
>  Bu yöntem, güvenilir olmayan verileri okunurken, herhangi bir kayıt defteri konumu belirtmek çağıranın sağlar. Ayrıca, [RegQueryValueEx](/windows/desktop/api/winreg/nf-winreg-regqueryvalueexa) bu yöntem tarafından kullanılan işlevi, NULL sonlandırılan dize açıkça işlemez. Her iki koşul için çağıran kod tarafından denetlenmelidir.

##  <a name="querystringvalue"></a>  CRegKey::QueryStringValue

Belirtilen değer adı için dize verileri almak için bu yöntemi çağırın.

```
LONG QueryStringValue(  
    LPCTSTR pszValueName,
    LPTSTR pszValue,
    ULONG* pnChars) throw();
```

### <a name="parameters"></a>Parametreler

*pszValueName*  
Sorgu için değerin adını içeren null ile sonlandırılmış bir dize işaretçisi.

*pszValue*  
Dize verileri alan arabellek için işaretçi.

*pnChars*  
TCHARs, işaret ettiği arabellek büyüklüğü *pszValue*. Yöntem döndürüldüğünde *pnChars* TCHARs, bir sonlandırıcı null karakter de dahil olmak üzere alınan, dizenin boyutunu içerir.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa ERROR_SUCCESS döndürülür. Bir değer okumak yöntem başarısız olursa WINERROR içinde tanımlanan bir sıfır olmayan hata kodu döndürür. H Başvurulan veri türü REG_SZ değil, ERROR_INVALID_DATA döndürülür. Yöntemi, ERROR_MORE_DATA döndürürse *pnChars* eşittir sıfır, gerekli arabellek boyutu bayt cinsinden değil.

### <a name="remarks"></a>Açıklamalar

Bu yöntemi kullanır `RegQueryValueEx` ve doğru veri türünü verdiğini onaylar. Bkz: [RegQueryValueEx](/windows/desktop/api/winreg/nf-winreg-regqueryvalueexa) daha fazla ayrıntı için.

> [!IMPORTANT]
>  Bu yöntem, güvenilir olmayan verileri okunurken, herhangi bir kayıt defteri konumu belirtmek çağıranın sağlar. Ayrıca, [RegQueryValueEx](/windows/desktop/api/winreg/nf-winreg-regqueryvalueexa) bu yöntem tarafından kullanılan işlevi, NULL sonlandırılan dize açıkça işlemez. Her iki koşul için çağıran kod tarafından denetlenmelidir.

##  <a name="queryvalue"></a>  CRegKey::QueryValue

Belirtilen değer alanı için verileri almak için bu yöntemi çağırın [m_hKey](#m_hkey). Bu yöntemin önceki sürümleri artık desteklenmemektedir ve ATL_DEPRECATED işaretlenir.

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

*pszValueName*  
Sorgu için değerin adını içeren null ile sonlandırılmış bir dize işaretçisi. Varsa *pszValueName* NULL veya boş bir dize, "", yöntemi türünü alır ve anahtarı için veri adlandırılmamış veya varsa varsayılan değer.

*pdwType*  
Belirtilen değerde depolanan verilerin türünü gösteren bir kod alan bir değişken işaretçisi. *PdwType* parametresi türü kodu gerekmiyorsa NULL olabilir.

*pData*  
Değer verisini alan arabellek için işaretçi. Veriler gerekli değilse bu parametre NULL olabilir.

*pnBytes*  
Arabelleğin bayt cinsinden boyutunu belirten bir değişken işaretçisi tarafından işaret edilen *pData* parametresi. Yöntem döndürüldüğünde, bu değişken kopyalanan verilerin boyutunu içeren *pData.*

*dwValue*  
Değer alanın sayısal veriler.

*lpszValueName*  
Sorgulanacak değer alanını belirtir.

*szValue*  
Değer alanın dize verileri.

*pdwCount*  
Dize veri boyutu. Değerini başlangıçta boyutuna ayarlanır *szValue* arabellek.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, ERROR_SUCCESS döndürür; Aksi takdirde, sıfır olmayan hata kodu WINERROR içinde tanımlanır. H

### <a name="remarks"></a>Açıklamalar

İki özgün sürümü `QueryValue` artık desteklenmemektedir ve ATL_DEPRECATED işaretlenir. Bu formlar kullanılırsa derleyici bir uyarı verir.

RegQueryValueEx kalan yöntemi çağırır.

> [!IMPORTANT]
>  Bu yöntem, güvenilir olmayan verileri okunurken, herhangi bir kayıt defteri konumu belirtmek çağıranın sağlar. Ayrıca, bu yöntem tarafından kullanılan RegQueryValueEx işlevi, NULL sonlandırılan dize açıkça işlemez. Her iki koşul için çağıran kod tarafından denetlenmelidir.

##  <a name="recursedeletekey"></a>  CRegKey::RecurseDeleteKey

Belirtilen anahtarı kayıt defterinden kaldırabilir ve tüm alt açıkça kaldırmak için bu yöntemi çağırın.

```
LONG RecurseDeleteKey(LPCTSTR lpszKey) throw();
```

### <a name="parameters"></a>Parametreler

*lpszKey*  
Silinecek anahtar adını belirtir. Bu ad, bir alt olmalıdır [m_hKey](#m_hkey).

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, ERROR_SUCCESS döndürür; Aksi takdirde, sıfır olmayan hata değeri WINERROR içinde tanımlanır. H

### <a name="remarks"></a>Açıklamalar

Anahtarı alt anahtarları varsa, anahtarı silmek için bu yöntemi çağırmanız gerekir.

##  <a name="setbinaryvalue"></a>  CRegKey::SetBinaryValue

İkili kayıt defteri anahtarı değerini ayarlamak için bu yöntemi çağırın.

```
LONG SetBinaryValue(  
    LPCTSTR pszValueName,
    const void* pValue,
    ULONG nBytes) throw();
```

### <a name="parameters"></a>Parametreler

*pszValueName*  
Ayarlanacak değerin adını içeren bir dize işaretçisi. Bu ada sahip bir değer zaten yoksa, yöntem anahtara ekler.

*pValue*  
Belirtilen değer adı ile depolanacak verileri içeren bir arabellek için işaretçi.

*nBytes*  
İşaret ettiği bilgiler bayt cinsinden boyutunu belirtir *pValue* parametresi.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, döndürülen değer ERROR_SUCCESS olur. Yöntem başarısız olursa, dönüş değeri WINERROR içinde tanımlanan bir sıfır olmayan hata kodudur. H

### <a name="remarks"></a>Açıklamalar

Bu yöntemde [RegSetValueEx](/windows/desktop/api/winreg/nf-winreg-regsetvalueexa) değeri kayıt defterine yazmak için.

##  <a name="setdwordvalue"></a>  CRegKey::SetDWORDValue

Kayıt defteri anahtarı DWORD değerini ayarlamak için bu yöntemi çağırın.

```
LONG SetDWORDValue(LPCTSTR pszValueName, DWORD dwValue) throw();
```

### <a name="parameters"></a>Parametreler

*pszValueName*  
Ayarlanacak değerin adını içeren bir dize işaretçisi. Bu ada sahip bir değer zaten yoksa, yöntem anahtara ekler.

*dwValue*  
Belirtilen değer adı ile depolanacak DWORD veriler.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, döndürülen değer ERROR_SUCCESS olur. Yöntem başarısız olursa, dönüş değeri WINERROR içinde tanımlanan bir sıfır olmayan hata kodudur. H

### <a name="remarks"></a>Açıklamalar

Bu yöntemde [RegSetValueEx](/windows/desktop/api/winreg/nf-winreg-regsetvalueexa) değeri kayıt defterine yazmak için.

##  <a name="setguidvalue"></a>  CRegKey::SetGUIDValue

Kayıt defteri anahtarının GUID değeri ayarlamak için bu yöntemi çağırın.

```
LONG SetGUIDValue(LPCTSTR pszValueName, REFGUID guidValue) throw();
```

### <a name="parameters"></a>Parametreler

*pszValueName*  
Ayarlanacak değerin adını içeren bir dize işaretçisi. Bu ada sahip bir değer zaten yoksa, yöntem anahtara ekler.

*guidValue*  
Belirtilen değer adı ile depolanacak GUID başvuru.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, döndürülen değer ERROR_SUCCESS olur. Yöntem başarısız olursa, dönüş değeri WINERROR içinde tanımlanan bir sıfır olmayan hata kodudur. H

### <a name="remarks"></a>Açıklamalar

Bu yöntemi kullanır `CRegKey::SetStringValue` ve kullanarak bir dize GUID dönüştürür [StringFromGUID2](/windows/desktop/api/combaseapi/nf-combaseapi-stringfromguid2).

##  <a name="setkeyvalue"></a>  CRegKey::SetKeyValue

Belirtilen anahtar belirtilen değer alanında verileri depolamak için bu yöntemi çağırın.

```
LONG SetKeyValue(  
    LPCTSTR lpszKeyName,
    LPCTSTR lpszValue,
    LPCTSTR lpszValueName = NULL) throw();
```

### <a name="parameters"></a>Parametreler

*lpszKeyName*  
Açılan veya oluşturulacak anahtar adını belirtir. Bu ad, bir alt olmalıdır [m_hKey](#m_hkey).

*lpszValue*  
Depolanan verileri belirtir. Bu parametre NULL olmayan olmalıdır.

*lpszValueName*  
Ayarlanacak değer alanını belirtir. Bu ada sahip bir değer alanı anahtarı zaten mevcut değilse eklenir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, ERROR_SUCCESS döndürür; Aksi takdirde, sıfır olmayan hata kodu WINERROR içinde tanımlanır. H

### <a name="remarks"></a>Açıklamalar

Açmak veya oluşturmak için bu yöntemi çağırın *lpszKeyName* anahtar ve depolamak *lpszValue* verilerinde *lpszValueName* değeri alanı.

##  <a name="setkeysecurity"></a>  CRegKey::SetKeySecurity

Kayıt defteri anahtarının güvenliğini ayarlamak için bu yöntemi çağırın.

```
LONG SetKeySecurity(SECURITY_INFORMATION si, PSECURITY_DESCRIPTOR psd) throw();
```

### <a name="parameters"></a>Parametreler

*sı*  
Ayarlamak için güvenlik tanımlayıcısı bileşenlerini belirtir. Değer aşağıdaki değerlerinin bir birleşimi olabilir:

|Değer|Açıklama|
|-----------|-------------|
|DACL_SECURITY_INFORMATION|Anahtarın isteğe bağlı erişim denetimi listesini (DACL) ayarlar. Çağırma işlemi nesnenin sahibi olmanız gerekir veya anahtar WRITE_DAC erişimi olmalıdır.|
|GROUP_SECURITY_INFORMATION|Anahtarın birincil grup güvenlik tanımlayıcısını (SID) ayarlar. Çağırma işlemi nesnenin sahibi olmanız gerekir veya anahtar WRITE_OWNER erişimi olmalıdır.|
|OWNER_SECURITY_INFORMATION|Anahtarın sahibi SID'si ayarlar. Anahtar WRITE_OWNER erişiminiz olmalıdır veya çağırma işlemine nesnenin sahibi olmanız veya etkin SE_TAKE_OWNERSHIP_NAME ayrıcalığına sahip olması gerekir.|
|SACL_SECURITY_INFORMATION|Anahtarın sistem erişim denetimi listesini (SACL) ayarlar. Anahtar ACCESS_SYSTEM_SECURITY erişiminiz olmalıdır. Bu erişim elde etmek için en uygun yolu SE_SECURITY_NAME etkinleştirmektir [ayrıcalık](https://msdn.microsoft.com/library/windows/desktop/aa379306) çağıranın geçerli erişim belirteci ACCESS_SYSTEM_SECURITY erişim için tanıtıcı açın ve ayrıcalık devre dışı bırakın.|

*PSD*  
İşaretçi bir [SECURITY_DESCRIPTOR](/windows/desktop/api/winnt/ns-winnt-_security_descriptor) belirtilen anahtar için ayarlanacak güvenlik özniteliklerini belirten yapısı.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, döndürülen değer ERROR_SUCCESS olur. Yöntem başarısız olursa, dönüş değeri WINERROR içinde tanımlanan bir sıfır olmayan hata kodudur. H

### <a name="remarks"></a>Açıklamalar

Anahtarın güvenlik öznitelikleri ayarlar. Bkz: [RegSetKeySecurity](/windows/desktop/api/winreg/nf-winreg-regsetkeysecurity) daha fazla ayrıntı için.

##  <a name="setmultistringvalue"></a>  CRegKey::SetMultiStringValue

Kayıt defteri anahtarının çok dizeli değer ayarlamak için bu yöntemi çağırın.

```
LONG SetMultiStringValue(LPCTSTR pszValueName, LPCTSTR pszValue) throw();
```

### <a name="parameters"></a>Parametreler

*pszValueName*  
Ayarlanacak değerin adını içeren bir dize işaretçisi. Bu ada sahip bir değer zaten yoksa, yöntem anahtara ekler.

*pszValue*  
Belirtilen değer adı ile depolanacak çok dizeli veri işaretçisi. Bir multistring iki null karakter ile sona erdi, null ile sonlandırılmış dizeler dizisidir.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, döndürülen değer ERROR_SUCCESS olur. Yöntem başarısız olursa, dönüş değeri WINERROR içinde tanımlanan bir sıfır olmayan hata kodudur. H

### <a name="remarks"></a>Açıklamalar

Bu yöntemde [RegSetValueEx](/windows/desktop/api/winreg/nf-winreg-regsetvalueexa) değeri kayıt defterine yazmak için.

##  <a name="setqwordvalue"></a>  CRegKey::SetQWORDValue

QWORD kayıt defteri anahtarı değerini ayarlamak için bu yöntemi çağırın.

```
LONG SetQWORDValue(LPCTSTR pszValueName, ULONGLONG qwValue) throw();
```

### <a name="parameters"></a>Parametreler

*pszValueName*  
Ayarlanacak değerin adını içeren bir dize işaretçisi. Bu ada sahip bir değer zaten yoksa, yöntem anahtara ekler.

*qwValue*  
Belirtilen değer adı ile depolanacak QWORD veriler.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, döndürülen değer ERROR_SUCCESS olur. Yöntem başarısız olursa, dönüş değeri WINERROR içinde tanımlanan bir sıfır olmayan hata kodudur. H

### <a name="remarks"></a>Açıklamalar

Bu yöntemde [RegSetValueEx](/windows/desktop/api/winreg/nf-winreg-regsetvalueexa) değeri kayıt defterine yazmak için.

##  <a name="setstringvalue"></a>  CRegKey::SetStringValue

Kayıt defteri anahtarının dize değerini ayarlamak için bu yöntemi çağırın.

```
LONG SetStringValue(  
    LPCTSTR pszValueName,
    LPCTSTR pszValue,
    DWORD dwType = REG_SZ) throw();
```

### <a name="parameters"></a>Parametreler

*pszValueName*  
Ayarlanacak değerin adını içeren bir dize işaretçisi. Bu ada sahip bir değer zaten yoksa, yöntem anahtara ekler.

*pszValue*  
Belirtilen değer adı ile depolanacak dize veri işaretçisi.

*dwType*  
Kayıt defterine yazılacak dizenin türü: REG_SZ (varsayılan) veya REG_EXPAND_SZ (çoklu dizeler için).

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, döndürülen değer ERROR_SUCCESS olur. Yöntem başarısız olursa, dönüş değeri WINERROR içinde tanımlanan bir sıfır olmayan hata kodudur. H

### <a name="remarks"></a>Açıklamalar

Bu yöntemde [RegSetValueEx](/windows/desktop/api/winreg/nf-winreg-regsetvalueexa) değeri kayıt defterine yazmak için.

##  <a name="setvalue"></a>  CRegKey::SetValue

Belirtilen değer alanında verileri depolamak için bu yöntemi çağırın [m_hKey](#m_hkey). Bu yöntemin önceki sürümleri artık desteklenmemektedir ve ATL_DEPRECATED işaretlenir.

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

*pszValueName*  
Ayarlanacak değerin adını içeren bir dize işaretçisi. Bu ada sahip bir değer anahtar mevcut değilse, yöntem anahtara ekler. Varsa *pszValueName* NULL veya boş bir dize, "", yöntem türünü ayarlar ve anahtarı için veri adlandırılmamış veya varsayılan değer.

*dwType*  
İşaret ettiği veri türünü gösteren bir kod belirtir *pValue* parametresi.

*pValue*  
Belirtilen değer adı ile depolanacak verileri içeren bir arabellek için işaretçi.

*nBytes*  
İşaret ettiği bilgiler bayt cinsinden boyutunu belirtir *pValue* parametresi. Veri türü REG_SZ, REG_EXPAND_SZ veya REG_MULTI_SZ ise *nBytes* sondaki boş karakter boyutunu eklemeniz gerekir.

*hKeyParent*  
Açık bir anahtar tanıtıcısı.

*lpszKeyName*  
Oluşturulacak veya açılan bir anahtarın adını belirtir. Bu ad, bir alt olmalıdır *hKeyParent*.

*lpszValue*  
Depolanan verileri belirtir. Bu parametre NULL olmayan olmalıdır.

*lpszValueName*  
Ayarlanacak değer alanını belirtir. Bu ada sahip bir değer alanı anahtarı zaten mevcut değilse eklenir.

*dwValue*  
Depolanan verileri belirtir.

*bMulti*  
False ise, dize türünde REG_SZ gösterir. TRUE ise, dize türü REG_MULTI_SZ bir multistring gösterilir.

*nValueLen*  
Varsa *bMulti* true ise *nValueLen* uzunluğu *lpszValue* karakter dizesi. Varsa *bMulti* yanlış, -1 değeri gösterir yöntemi uzunluğu otomatik olarak hesaplar.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, ERROR_SUCCESS döndürür; Aksi takdirde, sıfır olmayan hata kodu WINERROR içinde tanımlanır. H

### <a name="remarks"></a>Açıklamalar

İki özgün sürümü `SetValue` ATL_DEPRECATED işaretlenir ve artık kullanılmamalıdır. Bu formlar kullanılırsa derleyici bir uyarı verir.

Üçüncü yöntem çağrılarını [RegSetValueEx](/windows/desktop/api/winreg/nf-winreg-regsetvalueexa).

## <a name="see-also"></a>Ayrıca Bkz.

[DCOM örnek](../../visual-cpp-samples.md)   
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
