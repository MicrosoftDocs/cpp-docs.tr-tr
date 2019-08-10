---
title: CRegKey sınıfı
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
ms.openlocfilehash: bce5a16dd8d6564b6a0d3fa0344fe5cb2303764f
ms.sourcegitcommit: 46d24d6e70c03e05484923d9efc6ed5150e96a64
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68915785"
---
# <a name="cregkey-class"></a>CRegKey sınıfı

Bu sınıf, sistem kayıt defterindeki girdileri işlemek için yöntemler sağlar.

> [!IMPORTANT]
>  Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
class CRegKey
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CRegKey:: CRegKey](#cregkey)|Oluşturucu.|
|[CRegKey:: ~ CRegKey](#dtor)|Yok edicisi.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CRegKey:: Attach](#attach)|`CRegKey` [M_hKey](#m_hkey) üye tanıtıcısını olarak `hKey`ayarlayarak nesnesine bir HKEY eklemek için bu yöntemi çağırın.|
|[CRegKey:: Close](#close)|[M_hKey](#m_hkey) üye tanıtıcısını serbest BıRAKMAK ve null olarak ayarlamak için bu yöntemi çağırın.|
|[CRegKey:: Create](#create)|Bir alt anahtarı `hKeyParent`olarak mevcut değilse, belirtilen anahtarı oluşturmak için bu yöntemi çağırın.|
|[CRegKey::D Eletealtanahtar](#deletesubkey)|Belirtilen anahtarı kayıt defterinden kaldırmak için bu yöntemi çağırın.|
|[CRegKey::D eleteValue](#deletevalue)|[M_hKey](#m_hkey)öğesinden bir değer alanı kaldırmak için bu yöntemi çağırın.|
|[CRegKey::D etach](#detach)|[M_hKey](#m_hkey) üye tanıtıcısını `CRegKey` nesneden ayırmak ve null olarak ayarlamak `m_hKey` için bu yöntemi çağırın.|
|[CRegKey:: EnumKey](#enumkey)|Açık kayıt defteri anahtarının alt anahtarlarını numaralandırmak için bu yöntemi çağırın.|
|[CRegKey:: Flush](#flush)|Açık kayıt defteri anahtarının tüm özniteliklerini kayıt defterine yazmak için bu yöntemi çağırın.|
|[CRegKey:: GetKeySecurity](#getkeysecurity)|Açık kayıt defteri anahtarını koruyan güvenlik tanımlayıcısının bir kopyasını almak için bu yöntemi çağırın.|
|[CRegKey:: NotifyChangeKeyValue](#notifychangekeyvalue)|Bu yöntem, çağrıyı yapana, açık kayıt defteri anahtarının özniteliklerine veya içeriğine ilişkin değişiklikler hakkında bilgilendirir.|
|[CRegKey:: Open](#open)|Belirtilen anahtarı açmak için bu yöntemi çağırın ve bu anahtarın tanıtıcısına [m_hKey](#m_hkey) ayarlayın.|
|[CRegKey:: QueryBinaryValue](#querybinaryvalue)|Belirtilen değer adı için ikili verileri almak üzere bu yöntemi çağırın.|
|[CRegKey:: QueryDWORDValue](#querydwordvalue)|Belirtilen değer adı için DWORD verilerini almak üzere bu yöntemi çağırın.|
|[CRegKey:: Queryguıddeğeri](#queryguidvalue)|Belirtilen değer adı için GUID verilerini almak üzere bu yöntemi çağırın.|
|[CRegKey:: QueryMultiStringValue](#querymultistringvalue)|Belirtilen değer adı için çok dizeli verileri almak üzere bu yöntemi çağırın.|
|[CRegKey:: QueryQWORDValue](#queryqwordvalue)|Belirtilen değer adı için QWORD verilerini almak üzere bu yöntemi çağırın.|
|[CRegKey:: QueryStringValue](#querystringvalue)|Belirtilen değer adı için dize verilerini almak üzere bu yöntemi çağırın.|
|[CRegKey:: QueryValue](#queryvalue)|[M_hKey](#m_hkey)öğesinin belirtilen değer alanı için verileri almak üzere bu yöntemi çağırın. Bu yöntemin önceki sürümleri artık desteklenmemektedir ve ATL_DEPRECATED olarak işaretlenir.|
|[CRegKey:: RecurseDeleteKey](#recursedeletekey)|Belirtilen anahtarı kayıt defterinden kaldırmak ve tüm alt anahtarları açıkça kaldırmak için bu yöntemi çağırın.|
|[CRegKey:: SetBinaryValue](#setbinaryvalue)|Kayıt defteri anahtarının ikili değerini ayarlamak için bu yöntemi çağırın.|
|[CRegKey:: SetDWORDValue](#setdwordvalue)|Kayıt defteri anahtarının DWORD değerini ayarlamak için bu yöntemi çağırın.|
|[CRegKey:: Setguiddeğeri](#setguidvalue)|Kayıt defteri anahtarının GUID değerini ayarlamak için bu yöntemi çağırın.|
|[CRegKey:: SetKeySecurity](#setkeysecurity)|Kayıt defteri anahtarının güvenliğini ayarlamak için bu yöntemi çağırın.|
|[CRegKey:: SetKeyValue](#setkeyvalue)|Belirtilen bir anahtarın belirtilen bir değer alanındaki verileri depolamak için bu yöntemi çağırın.|
|[CRegKey:: SetMultiStringValue](#setmultistringvalue)|Kayıt defteri anahtarının MultiString değerini ayarlamak için bu yöntemi çağırın.|
|[CRegKey:: SetQWORDValue](#setqwordvalue)|Kayıt defteri anahtarının QWORD değerini ayarlamak için bu yöntemi çağırın.|
|[CRegKey:: SetStringValue](#setstringvalue)|Kayıt defteri anahtarının dize değerini ayarlamak için bu yöntemi çağırın.|
|[CRegKey:: SetValue](#setvalue)|[M_hKey](#m_hkey)'in belirtilen değer alanına veri depolamak için bu yöntemi çağırın. Bu yöntemin önceki sürümleri artık desteklenmemektedir ve ATL_DEPRECATED olarak işaretlenir.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CRegKey:: operator HKEY](#operator_hkey)|Bir `CRegKey` nesneyi bir HKEY öğesine dönüştürür.|
|[CRegKey:: operator =](#operator_eq)|Atama işleci.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CRegKey:: m_hKey](#m_hkey)|`CRegKey` Nesnesiyle ilişkili kayıt defteri anahtarının bir işleyicisini içerir.|
|[CRegKey:: m_pTM](#m_ptm)|`CAtlTransactionManager` Nesne işaretçisi|

## <a name="remarks"></a>Açıklamalar

`CRegKey`Sistem kayıt defterinde anahtar ve değer oluşturmak ve silmek için yöntemler sağlar. Kayıt defteri, yazılım sürüm numaraları, yüklü donanımın mantıksal-fiziksek eşlemeleri ve COM nesneleri gibi sistem bileşenleri için yüklemeye özgü bir tanımlar kümesi içerir.

`CRegKey`belirli bir makine için sistem kayıt defterine bir programlama arabirimi sağlar. Örneğin, belirli bir kayıt defteri anahtarını açmak için çağrısı `CRegKey::Open`yapın. Bir veri değerini almak veya değiştirmek için sırasıyla veya `CRegKey::QueryValue` `CRegKey::SetValue`' ı çağırın. Bir anahtarı kapatmak için çağrısı `CRegKey::Close`yapın.

Bir anahtarı kapattığınızda, kayıt defteri verileri sabit diske yazılır (temizlenir). Bu işlem birkaç saniye sürebilir. Uygulamanızın kayıt defteri verilerini sabit diske açıkça yazması gerekiyorsa, [RegFlushKey](/windows/desktop/api/winreg/nf-winreg-regflushkey) Win32 işlevini çağırabilirsiniz. Ancak, `RegFlushKey` birçok sistem kaynağını kullanır ve yalnızca kesinlikle gerekli olduğunda çağrılmalıdır.

> [!IMPORTANT]
>  Çağıranın bir kayıt defteri konumu belirtmesini sağlayan yöntemlerin, güvenilir olmayan verileri okuma olasılığı vardır. [RegQueryValueEx](/windows/desktop/api/winreg/nf-winreg-regqueryvalueexa) 'yi kullanan Yöntemler, bu işlevin null olarak sonlandırılmış dizeleri açıkça işlemediğini dikkate almalıdır. Her iki koşul de çağıran kod tarafından denetlenmelidir.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase. h

##  <a name="attach"></a>CRegKey:: Attach

`CRegKey` [M_hKey](#m_hkey) üye tanıtıcısını *HKEY*olarak ayarlayarak nesnesine bir HKEY eklemek için bu yöntemi çağırın.

```
void Attach(HKEY hKey) throw();
```

### <a name="parameters"></a>Parametreler

*hKey*<br/>
Kayıt defteri anahtarının tanıtıcısı.

### <a name="remarks"></a>Açıklamalar

`Attach``m_hKey` null değilse onay olur.

##  <a name="close"></a>CRegKey:: Close

[M_hKey](#m_hkey) üye tanıtıcısını serbest BıRAKMAK ve null olarak ayarlamak için bu yöntemi çağırın.

```
LONG Close() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, ERROR_SUCCESS döndürür; Aksi takdirde bir hata değeri döndürür.

##  <a name="create"></a>CRegKey:: Create

Bir *hKeyParent*alt anahtarı olarak yoksa, belirtilen anahtarı oluşturmak için bu yöntemi çağırın.

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
Açık bir anahtarın tanıtıcısı.

*lpszKeyName*<br/>
Oluşturulacak veya açılacak bir anahtarın adını belirtir. Bu ad, *hKeyParent*'nin bir alt anahtarı olmalıdır.

*lpszClass*<br/>
Oluşturulacak veya açılacak anahtarın sınıfını belirtir. Varsayılan değer REG_NONE ' dir.

*dwOptions*<br/>
Anahtar seçenekleri. Varsayılan değer REG_OPTION_NON_VOLATILE ' dir. Olası değerler ve açıklamaların bir listesi için, bkz. [RegCreateKeyEx](/windows/desktop/api/winreg/nf-winreg-regcreatekeyexa) in Windows SDK.

*samDesired*<br/>
Anahtar için güvenlik erişimi. Varsayılan değer KEY_READ &#124; KEY_WRITE ' dir. Olası değerler ve açıklamaların bir listesi için bkz `RegCreateKeyEx`.

*lpSecAttr*<br/>
Anahtar tanıtıcısının bir alt işlem tarafından devralınıp alınmayacağını belirten bir [SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\)) yapısına yönelik işaretçi. Varsayılan olarak, bu parametre NULL (tanıtıcı devralınamaz anlamına gelir).

*lpdwDisposition*<br/>
dışı NULL olmayan, REG_CREATED_NEW_KEY (anahtar yoksa ve oluşturulduysa) ya da REG_OPENED_EXISTING_KEY (anahtar varsa ve açılırsa) alır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, ERROR_SUCCESS döndürür ve anahtarı açar. Yöntem başarısız olursa, dönüş değeri, WINERROR 'da tanımlanan sıfır dışı bir hata kodudur. Olsun.

### <a name="remarks"></a>Açıklamalar

`Create`[m_hKey](#m_hkey) üyesini bu anahtarın tanıtıcısına ayarlar.

##  <a name="cregkey"></a>CRegKey:: CRegKey

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

*hKey*<br/>
Kayıt defteri anahtarı için bir tanıtıcı.

*pTM*<br/>
CAtlTransactionManager nesnesine yönelik işaretçi

### <a name="remarks"></a>Açıklamalar

Yeni `CRegKey` bir nesne oluşturur. Nesne varolan `CRegKey` bir nesneden veya bir işleyicinizden bir kayıt defteri anahtarına oluşturulabilir.

##  <a name="dtor"></a>CRegKey:: ~ CRegKey

Yok edicisi.

```
~CRegKey() throw();
```

### <a name="remarks"></a>Açıklamalar

Yıkıcı yayınlar `m_hKey`.

##  <a name="deletesubkey"></a>CRegKey::D Eletealtanahtar

Belirtilen anahtarı kayıt defterinden kaldırmak için bu yöntemi çağırın.

```
LONG DeleteSubKey(LPCTSTR lpszSubKey) throw();
```

### <a name="parameters"></a>Parametreler

*lpszSubKey*<br/>
Silinecek anahtarın adını belirtir. Bu ad [m_hKey](#m_hkey)bir alt anahtar olmalıdır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, ERROR_SUCCESS döndürür. Yöntem başarısız olursa, dönüş değeri, WINERROR 'da tanımlanan sıfır dışı bir hata kodudur. Olsun.

### <a name="remarks"></a>Açıklamalar

`DeleteSubKey`yalnızca alt anahtarı olmayan bir anahtar silinebilir. Anahtarın alt anahtarları varsa, bunun yerine [RecurseDeleteKey](#recursedeletekey) çağırın.

##  <a name="deletevalue"></a>CRegKey::D eleteValue

[M_hKey](#m_hkey)öğesinden bir değer alanı kaldırmak için bu yöntemi çağırın.

```
LONG DeleteValue(LPCTSTR lpszValue) throw();
```

### <a name="parameters"></a>Parametreler

*lpszValue*<br/>
Kaldırılacak değer alanını belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, ERROR_SUCCESS döndürür. Yöntem başarısız olursa, dönüş değeri, WINERROR 'da tanımlanan sıfır dışı bir hata kodudur. Olsun.

##  <a name="detach"></a>CRegKey::D etach

[M_hKey](#m_hkey) üye tanıtıcısını `CRegKey` nesneden ayırmak ve null olarak ayarlamak `m_hKey` için bu yöntemi çağırın.

```
HKEY Detach() throw();
```

### <a name="return-value"></a>Dönüş Değeri

`CRegKey` Nesneyle ilişkili HKEY.

##  <a name="enumkey"></a>CRegKey:: EnumKey

Açık kayıt defteri anahtarının alt anahtarlarını numaralandırmak için bu yöntemi çağırın.

```
LONG EnumKey(
    DWORD iIndex,
    LPTSTR pszName,
    LPDWORD pnNameLength,
    FILETIME* pftLastWriteTime = NULL) throw();
```

### <a name="parameters"></a>Parametreler

*IIndex*<br/>
Alt anahtar dizini. Bu parametre ilk çağrı için sıfır olmalı ve ardından sonraki çağrılar için artırılır

*pszName*<br/>
Sonlandırıcı null karakteri de dahil olmak üzere alt anahtarın adını alan bir arabelleğin işaretçisi. Tam anahtar hiyerarşisine değil, yalnızca alt anahtarın adı arabelleğe kopyalanır.

*pnNameLength*<br/>
*PszName* parametresi tarafından belirtilen arabelleğin TCHARs cinsinden boyutunu belirten bir değişkene yönelik işaretçi. Bu boyut, Sonlandırıcı null karakterini içermelidir. Yöntem döndüğünde, *pnNameLength* tarafından işaret edilen değişken arabellekte depolanan karakter sayısını içerir. Döndürülen sayı, Sonlandırıcı null karakterini içermiyor.

*pftLastWriteTime*<br/>
Numaralandırılmış alt anahtarın son yazıldığı saati alan bir değişkene yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, dönüş değeri ERROR_SUCCESS olur. Yöntem başarısız olursa, dönüş değeri, WINERROR 'da tanımlanan sıfır dışı bir hata kodudur. Olsun.

### <a name="remarks"></a>Açıklamalar

Alt anahtarları numaralandırmak için, sıfır `CRegKey::EnumKey` diziniyle çağırın. Dizin değerini artırın ve Yöntem ERROR_NO_MORE_ITEMS dönene kadar tekrarlayın. Daha fazla bilgi için Windows SDK [RegEnumKeyEx](/windows/desktop/api/winreg/nf-winreg-regenumkeyexa) bakın.

##  <a name="flush"></a>CRegKey:: Flush

Açık kayıt defteri anahtarının tüm özniteliklerini kayıt defterine yazmak için bu yöntemi çağırın.

```
LONG Flush() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, dönüş değeri ERROR_SUCCESS olur. Yöntem başarısız olursa, dönüş değeri, WINERROR 'da tanımlanan sıfır dışı bir hata kodudur. Olsun.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için Windows SDK bkz. [RegEnumFlush](/windows/desktop/api/winreg/nf-winreg-regflushkey) .

##  <a name="getkeysecurity"></a>CRegKey:: GetKeySecurity

Açık kayıt defteri anahtarını koruyan güvenlik tanımlayıcısının bir kopyasını almak için bu yöntemi çağırın.

```
LONG GetKeySecurity(
    SECURITY_INFORMATION si,
    PSECURITY_DESCRIPTOR psd,
    LPDWORD pnBytes) throw();
```

### <a name="parameters"></a>Parametreler

*ortası*<br/>
İstenen güvenlik bilgilerini gösteren [SECURITY_INFORMATION](/windows/desktop/SecAuthZ/security-information) değeri.

*PSD*<br/>
İstenen güvenlik tanımlayıcısının kopyasını alan bir arabelleğin işaretçisi.

*pnBytes*<br/>
*PSD*tarafından işaret edilen arabelleğin bayt cinsinden boyutu.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, dönüş değeri ERROR_SUCCESS olur. Yöntem başarısız olursa, dönüş değeri bir sıfır dışı hata kodu, WINERROR içinde tanımlanır. Olsun.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [RegGetKeySecurity](/windows/desktop/api/winreg/nf-winreg-reggetkeysecurity).

##  <a name="m_hkey"></a>CRegKey:: m_hKey

`CRegKey` Nesnesiyle ilişkili kayıt defteri anahtarının bir işleyicisini içerir.

```
HKEY m_hKey;
```

##  <a name="m_ptm"></a>CRegKey:: m_pTM

Bir `CAtlTransactionManager` nesne işaretçisi.

```
CAtlTransactionManager* m_pTM;
```

### <a name="remarks"></a>Açıklamalar

##  <a name="notifychangekeyvalue"></a>CRegKey:: NotifyChangeKeyValue

Bu yöntem, çağrıyı yapana, açık kayıt defteri anahtarının özniteliklerine veya içeriğine ilişkin değişiklikler hakkında bilgilendirir.

```
LONG NotifyChangeKeyValue(
    BOOL bWatchSubtree,
    DWORD dwNotifyFilter,
    HANDLE hEvent,
    BOOL bAsync = TRUE) throw();
```

### <a name="parameters"></a>Parametreler

*bWatchSubtree*<br/>
Belirtilen anahtarda ve tüm alt anahtarlarından veya yalnızca belirtilen anahtarda değişiklik yapılıp yapılmayacağını belirten bir bayrak belirtir. Bu parametre TRUE ise, yöntemi anahtardaki ve alt anahtarlarından değişiklikleri raporlar. Parametre FALSE ise, yöntem yalnızca anahtardaki değişiklikleri raporlar.

*dwNotifyFilter*<br/>
Hangi değişikliklerin bildirilmesi gerektiğini denetleyen bir bayrak kümesi belirtir. Bu parametre aşağıdaki değerlerin bir birleşimi olabilir:

|Değer|Açıklama|
|-----------|-------------|
|REG_NOTIFY_CHANGE_NAME|Bir alt anahtar eklendiğinde veya silinirse çağrıyı yapana bildirin.|
|REG_NOTIFY_CHANGE_ATTRIBUTES|Güvenlik tanımlayıcısı bilgileri gibi, anahtarın özniteliklerinde değişiklik çağıranına bildirim gönderin.|
|REG_NOTIFY_CHANGE_LAST_SET|Anahtarın bir değerindeki değişiklik çağıranına bildirim gönderin. Bu, bir değer ekleme veya silme ya da varolan bir değeri değiştirme içerebilir.|
|REG_NOTIFY_CHANGE_SECURITY|Anahtarın güvenlik tanımlayıcısına çağrı çağıranına bildirin.|

*hEvent*<br/>
Bir olayı işleyin. *BAsync* parametresi true ise, yöntem hemen döndürülür ve değişiklikler bu olaya sinyal vererek raporlanır. *BAsync* yanlış Ise, *hEvent* yok sayılır.

*bAsync*<br/>
Yöntemin değişiklikleri nasıl raporlandığını gösteren bir bayrak belirtir. Bu parametre TRUE ise, yöntemi hemen döndürür ve belirtilen olay sinyallere göre değişiklikleri raporlar. Bu parametre FALSE olduğunda, bir değişiklik gerçekleşene kadar Yöntem döndürmez. *HEvent* geçerli bir olay belirtmezse *BASYNC* parametresi true olamaz.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, dönüş değeri ERROR_SUCCESS olur. Yöntem başarısız olursa, dönüş değeri, WINERROR 'da tanımlanan sıfır dışı bir hata kodudur. Olsun.

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
>  Bu yöntem, belirtilen anahtar silinirse çağrıyı yapana bildirmez.

Daha fazla bilgi ve örnek program için bkz. [RegNotifyChangeKeyValue](/windows/desktop/api/winreg/nf-winreg-regnotifychangekeyvalue).

##  <a name="open"></a>CRegKey:: Open

Belirtilen anahtarı açmak için bu yöntemi çağırın ve bu anahtarın tanıtıcısına [m_hKey](#m_hkey) ayarlayın.

```
LONG Open(
    HKEY hKeyParent,
    LPCTSTR lpszKeyName,
    REGSAM samDesired = KEY_READ | KEY_WRITE) throw();
```

### <a name="parameters"></a>Parametreler

*hKeyParent*<br/>
Açık bir anahtarın tanıtıcısı.

*lpszKeyName*<br/>
Oluşturulacak veya açılacak bir anahtarın adını belirtir. Bu ad, *hKeyParent*'nin bir alt anahtarı olmalıdır.

*samDesired*<br/>
Anahtar için güvenlik erişimi. Varsayılan değer KEY_ALL_ACCESS ' dir. Olası değerler ve açıklamaların bir listesi için, bkz. [RegCreateKeyEx](/windows/desktop/api/winreg/nf-winreg-regcreatekeyexa) in Windows SDK.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, ERROR_SUCCESS döndürür; Aksi halde, WINERROR 'da sıfır olmayan bir hata değeri tanımlandı. Olsun.

### <a name="remarks"></a>Açıklamalar

*LpszKeyName* parametresi null veya boş bir dizeye işaret ediyorsa, `Open` *hKeyParent*tarafından tanımlanan anahtarın yeni bir işleyicisini açar, ancak daha önce açılmış bir tanıtıcıyı kapatmaz.

[CRegKey:: Create](#create)' in `Open` aksine, mevcut değilse belirtilen anahtarı oluşturmaz.

##  <a name="operator_hkey"></a>CRegKey:: operator HKEY

Bir `CRegKey` nesneyi bir HKEY öğesine dönüştürür.

```
operator HKEY() const throw();
```

##  <a name="operator_eq"></a>CRegKey:: operator =

Atama işleci.

```
CRegKey& operator= (CRegKey& key) throw();
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Kopyalanacak anahtar.

### <a name="return-value"></a>Dönüş Değeri

Yeni anahtara bir başvuru döndürür.

### <a name="remarks"></a>Açıklamalar

Bu işleç, *anahtarı* geçerli nesnesinden ayırır ve bunun yerine `CRegKey` nesnesine atar.

##  <a name="querybinaryvalue"></a>CRegKey:: QueryBinaryValue

Belirtilen değer adı için ikili verileri almak üzere bu yöntemi çağırın.

```
LONG QueryBinaryValue(
    LPCTSTR pszValueName,
    void* pValue,
    ULONG* pnBytes) throw();
```

### <a name="parameters"></a>Parametreler

*pszValueName*<br/>
Sorgulanacak değerin adını içeren, null ile sonlandırılmış bir dize işaretçisi.

*pValue*<br/>
Değerin verilerini alan bir arabelleğin işaretçisi.

*pnBytes*<br/>
*PValue* parametresi tarafından işaret edilen arabelleğin bayt cinsinden boyutunu belirten bir değişkene yönelik işaretçi. Yöntem döndüğünde, bu değişken arabelleğe kopyalanmış verilerin boyutunu içerir.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, ERROR_SUCCESS döndürülür. Yöntem bir değeri okuyamazsa, WINERROR 'da tanımlanan sıfır olmayan bir hata kodu döndürür. Olsun. Başvurulan veriler REG_BıNARY türünde değilse, ERROR_INVALID_DATA döndürülür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, ' nin `RegQueryValueEx` kullanımını sağlar ve doğru türde verilerin döndürüldüğünü onaylar. Daha fazla ayrıntı için bkz. [RegQueryValueEx](/windows/desktop/api/winreg/nf-winreg-regqueryvalueexa) .

> [!IMPORTANT]
>  Bu yöntem, çağıranın hiçbir kayıt defteri konumu belirtmesini sağlar. Bu, güvenilmez olmayan verileri okuyabilir. Ayrıca, bu yöntem tarafından kullanılan [RegQueryValueEx](/windows/desktop/api/winreg/nf-winreg-regqueryvalueexa) IşLEVI, null olarak sonlandırılmış dizeleri açıkça işlemez. Her iki koşul de çağıran kod tarafından denetlenmelidir.

##  <a name="querydwordvalue"></a>CRegKey:: QueryDWORDValue

Belirtilen değer adı için DWORD verilerini almak üzere bu yöntemi çağırın.

```
LONG QueryDWORDValue(
    LPCTSTR pszValueName,
    DWORD& dwValue) throw();
```

### <a name="parameters"></a>Parametreler

*pszValueName*<br/>
Sorgulanacak değerin adını içeren, null ile sonlandırılmış bir dize işaretçisi.

*dwValue*<br/>
DWORD değerini alan bir arabelleğin işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, ERROR_SUCCESS döndürülür. Yöntem bir değeri okuyamazsa, WINERROR 'da tanımlanan sıfır olmayan bir hata kodu döndürür. Olsun. Başvurulan veriler REG_DWORD türünde değilse, ERROR_INVALID_DATA döndürülür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, ' nin `RegQueryValueEx` kullanımını sağlar ve doğru türde verilerin döndürüldüğünü onaylar. Daha fazla ayrıntı için bkz. [RegQueryValueEx](/windows/desktop/api/winreg/nf-winreg-regqueryvalueexa) .

> [!IMPORTANT]
>  Bu yöntem, çağıranın hiçbir kayıt defteri konumu belirtmesini sağlar. Bu, güvenilmez olmayan verileri okuyabilir. Ayrıca, bu yöntem tarafından kullanılan [RegQueryValueEx](/windows/desktop/api/winreg/nf-winreg-regqueryvalueexa) IşLEVI, null olarak sonlandırılmış dizeleri açıkça işlemez. Her iki koşul de çağıran kod tarafından denetlenmelidir.

##  <a name="queryguidvalue"></a>CRegKey:: Queryguıddeğeri

Belirtilen değer adı için GUID verilerini almak üzere bu yöntemi çağırın.

```
LONG QueryGUIDValue(
    LPCTSTR pszValueName,
    GUID& guidValue) throw();
```

### <a name="parameters"></a>Parametreler

*pszValueName*<br/>
Sorgulanacak değerin adını içeren, null ile sonlandırılmış bir dize işaretçisi.

*GUIDDeğeri*<br/>
GUID 'ı alan bir değişkene yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, ERROR_SUCCESS döndürülür. Yöntem bir değeri okuyamazsa, WINERROR 'da tanımlanan sıfır olmayan bir hata kodu döndürür. Olsun. Başvurulan veriler geçerli bir GUID değilse, ERROR_INVALID_DATA döndürülür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, ' nin `CRegKey::QueryStringValue` kullanımını sağlar ve [clsidfromstring](/windows/desktop/api/combaseapi/nf-combaseapi-clsidfromstring)kullanarak dizeyi bir GUID 'ye dönüştürür.

> [!IMPORTANT]
>  Bu yöntem, çağıranın hiçbir kayıt defteri konumu belirtmesini sağlar. Bu, güvenilmez olmayan verileri okuyabilir.

##  <a name="querymultistringvalue"></a>CRegKey:: QueryMultiStringValue

Belirtilen değer adı için çok dizeli verileri almak üzere bu yöntemi çağırın.

```
LONG QueryMultiStringValue(
    LPCTSTR pszValueName,
    LPTSTR pszValue,
    ULONG* pnChars) throw();
```

### <a name="parameters"></a>Parametreler

*pszValueName*<br/>
Sorgulanacak değerin adını içeren, null ile sonlandırılmış bir dize işaretçisi.

*pszValue*<br/>
Çok dizeli verileri alan bir arabelleğin işaretçisi. Çoklu dize, null ile sonlandırılmış dizelerin dizileridir ve iki null karakterle sonlandırılır.

*pnChar 'lar*<br/>
*PszValue*tarafından işaret edilen arabelleğin, TCHARs cinsinden boyutu. Yöntem döndürüldüğünde, *pnChar* , bir Sonlandırıcı null karakteri de dahil olmak üzere çok dizeli alınan, TCHARs cinsinden boyutu içerir.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, ERROR_SUCCESS döndürülür. Yöntem bir değeri okuyamazsa, WINERROR 'da tanımlanan sıfır olmayan bir hata kodu döndürür. Olsun. Başvurulan veriler REG_MULTI_SZ türünde değilse, ERROR_INVALID_DATA döndürülür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, ' nin `RegQueryValueEx` kullanımını sağlar ve doğru türde verilerin döndürüldüğünü onaylar. Daha fazla ayrıntı için bkz. [RegQueryValueEx](/windows/desktop/api/winreg/nf-winreg-regqueryvalueexa) .

> [!IMPORTANT]
>  Bu yöntem, çağıranın hiçbir kayıt defteri konumu belirtmesini sağlar. Bu, güvenilmez olmayan verileri okuyabilir. Ayrıca, bu yöntem tarafından kullanılan [RegQueryValueEx](/windows/desktop/api/winreg/nf-winreg-regqueryvalueexa) IşLEVI, null olarak sonlandırılmış dizeleri açıkça işlemez. Her iki koşul de çağıran kod tarafından denetlenmelidir.

##  <a name="queryqwordvalue"></a>CRegKey:: QueryQWORDValue

Belirtilen değer adı için QWORD verilerini almak üzere bu yöntemi çağırın.

```
LONG QueryQWORDValue(
    LPCTSTR pszValueName,
    ULONGLONG& qwValue) throw();
```

### <a name="parameters"></a>Parametreler

*pszValueName*<br/>
Sorgulanacak değerin adını içeren, null ile sonlandırılmış bir dize işaretçisi.

*qwValue*<br/>
QWORD alan bir arabelleğin işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, ERROR_SUCCESS döndürülür. Yöntem bir değeri okuyamazsa, WINERROR 'da tanımlanan sıfır olmayan bir hata kodu döndürür. Olsun. Başvurulan veriler REG_QWORD türünde değilse, ERROR_INVALID_DATA döndürülür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, ' nin `RegQueryValueEx` kullanımını sağlar ve doğru türde verilerin döndürüldüğünü onaylar. Daha fazla ayrıntı için bkz. [RegQueryValueEx](/windows/desktop/api/winreg/nf-winreg-regqueryvalueexa) .

> [!IMPORTANT]
>  Bu yöntem, çağıranın hiçbir kayıt defteri konumu belirtmesini sağlar. Bu, güvenilmez olmayan verileri okuyabilir. Ayrıca, bu yöntem tarafından kullanılan [RegQueryValueEx](/windows/desktop/api/winreg/nf-winreg-regqueryvalueexa) IşLEVI, null olarak sonlandırılmış dizeleri açıkça işlemez. Her iki koşul de çağıran kod tarafından denetlenmelidir.

##  <a name="querystringvalue"></a>CRegKey:: QueryStringValue

Belirtilen değer adı için dize verilerini almak üzere bu yöntemi çağırın.

```
LONG QueryStringValue(
    LPCTSTR pszValueName,
    LPTSTR pszValue,
    ULONG* pnChars) throw();
```

### <a name="parameters"></a>Parametreler

*pszValueName*<br/>
Sorgulanacak değerin adını içeren, null ile sonlandırılmış bir dize işaretçisi.

*pszValue*<br/>
Dize verilerini alan bir arabelleğin işaretçisi.

*pnChar 'lar*<br/>
*PszValue*tarafından işaret edilen arabelleğin, TCHARs cinsinden boyutu. Yöntemi döndürüldüğünde, *pnChar* , bir Sonlandırıcı null karakteri de dahil olmak üzere, alınan dizenin TCHARs cinsinden boyutunu içerir.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, ERROR_SUCCESS döndürülür. Yöntem bir değeri okuyamazsa, WINERROR 'da tanımlanan sıfır olmayan bir hata kodu döndürür. Olsun. Başvurulan veriler REG_SZ türünde değilse, ERROR_INVALID_DATA döndürülür. Yöntem ERROR_MORE_DATA döndürürse, *pnChar* 'lar, gerekli arabellek boyutunu bayt cinsinden değil, sıfıra eşit.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, ' nin `RegQueryValueEx` kullanımını sağlar ve doğru türde verilerin döndürüldüğünü onaylar. Daha fazla ayrıntı için bkz. [RegQueryValueEx](/windows/desktop/api/winreg/nf-winreg-regqueryvalueexa) .

> [!IMPORTANT]
>  Bu yöntem, çağıranın hiçbir kayıt defteri konumu belirtmesini sağlar. Bu, güvenilmez olmayan verileri okuyabilir. Ayrıca, bu yöntem tarafından kullanılan [RegQueryValueEx](/windows/desktop/api/winreg/nf-winreg-regqueryvalueexa) IşLEVI, null olarak sonlandırılmış dizeleri açıkça işlemez. Her iki koşul de çağıran kod tarafından denetlenmelidir.

##  <a name="queryvalue"></a>CRegKey:: QueryValue

[M_hKey](#m_hkey)öğesinin belirtilen değer alanı için verileri almak üzere bu yöntemi çağırın. Bu yöntemin önceki sürümleri artık desteklenmemektedir ve ATL_DEPRECATED olarak işaretlenir.

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
Sorgulanacak değerin adını içeren, null ile sonlandırılmış bir dize işaretçisi. *PszValueName* null veya boş bir dize, "" ise, yöntemi anahtarın adlandırılmamış veya varsayılan değeri için türü ve verileri alır.

*pdwType*<br/>
Belirtilen değerde depolanan veri türünü gösteren bir kod alan bir değişkene yönelik işaretçi. Tür kodu gerekmiyorsa *pdwType* parametresi null olabilir.

*pData*<br/>
Değerin verilerini alan bir arabelleğin işaretçisi. Veriler gerekmiyorsa bu parametre NULL olabilir.

*pnBytes*<br/>
*PData* parametresi tarafından işaret edilen arabelleğin bayt cinsinden boyutunu belirten bir değişkene yönelik işaretçi. Yöntem döndüğünde, bu değişken *pData* 'a kopyalanmış verilerin boyutunu içerir.

*dwValue*<br/>
Değer alanının sayısal verileri.

*lpszValueName*<br/>
Sorgulanacak değer alanını belirtir.

*szValue*<br/>
Değer alanının dize verileri.

*pdwCount*<br/>
Dize verilerinin boyutu. Değeri başlangıçta *szValue* arabelleğinin boyutuna ayarlanır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, ERROR_SUCCESS döndürür; Aksi halde, WINERROR 'da tanımlanmış sıfır olmayan bir hata kodu. Olsun.

### <a name="remarks"></a>Açıklamalar

Öğesinin `QueryValue` iki orijinal sürümü artık desteklenmemektedir ve ATL_DEPRECATED olarak işaretlenir. Bu formlar kullanılıyorsa derleyici bir uyarı oluşturur.

Kalan Yöntem RegQueryValueEx çağırır.

> [!IMPORTANT]
>  Bu yöntem, çağıranın hiçbir kayıt defteri konumu belirtmesini sağlar. Bu, güvenilmez olmayan verileri okuyabilir. Ayrıca, bu yöntem tarafından kullanılan RegQueryValueEx işlevi, NULL olarak sonlandırılmış dizeleri açıkça işlemez. Her iki koşul de çağıran kod tarafından denetlenmelidir.

##  <a name="recursedeletekey"></a>CRegKey:: RecurseDeleteKey

Belirtilen anahtarı kayıt defterinden kaldırmak ve tüm alt anahtarları açıkça kaldırmak için bu yöntemi çağırın.

```
LONG RecurseDeleteKey(LPCTSTR lpszKey) throw();
```

### <a name="parameters"></a>Parametreler

*lpszKey*<br/>
Silinecek anahtarın adını belirtir. Bu ad [m_hKey](#m_hkey)bir alt anahtar olmalıdır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, ERROR_SUCCESS döndürür; Aksi halde, WINERROR 'da sıfır olmayan bir hata değeri tanımlandı. Olsun.

### <a name="remarks"></a>Açıklamalar

Anahtarın alt anahtarları varsa, anahtarı silmek için bu yöntemi çağırmanız gerekir.

##  <a name="setbinaryvalue"></a>CRegKey:: SetBinaryValue

Kayıt defteri anahtarının ikili değerini ayarlamak için bu yöntemi çağırın.

```
LONG SetBinaryValue(
    LPCTSTR pszValueName,
    const void* pValue,
    ULONG nBytes) throw();
```

### <a name="parameters"></a>Parametreler

*pszValueName*<br/>
Ayarlanacak değerin adını içeren bir dize işaretçisi. Bu ada sahip bir değer zaten yoksa, yöntemi anahtara ekler.

*pValue*<br/>
Belirtilen değer adıyla depolanacak verileri içeren bir arabelleğin işaretçisi.

*nBytes*<br/>
*PValue* parametresi tarafından işaret edilen bilgilerin boyutunu bayt cinsinden belirtir.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, dönüş değeri ERROR_SUCCESS olur. Yöntem başarısız olursa, dönüş değeri, WINERROR 'da tanımlanan sıfır dışı bir hata kodudur. Olsun.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, kayıt defterine değeri yazmak için [RegSetValueEx](/windows/desktop/api/winreg/nf-winreg-regsetvalueexa) kullanır.

##  <a name="setdwordvalue"></a>CRegKey:: SetDWORDValue

Kayıt defteri anahtarının DWORD değerini ayarlamak için bu yöntemi çağırın.

```
LONG SetDWORDValue(LPCTSTR pszValueName, DWORD dwValue) throw();
```

### <a name="parameters"></a>Parametreler

*pszValueName*<br/>
Ayarlanacak değerin adını içeren bir dize işaretçisi. Bu ada sahip bir değer zaten yoksa, yöntemi anahtara ekler.

*dwValue*<br/>
Belirtilen değer adıyla depolanacak DWORD verileri.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, dönüş değeri ERROR_SUCCESS olur. Yöntem başarısız olursa, dönüş değeri, WINERROR 'da tanımlanan sıfır dışı bir hata kodudur. Olsun.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, kayıt defterine değeri yazmak için [RegSetValueEx](/windows/desktop/api/winreg/nf-winreg-regsetvalueexa) kullanır.

##  <a name="setguidvalue"></a>CRegKey:: Setguiddeğeri

Kayıt defteri anahtarının GUID değerini ayarlamak için bu yöntemi çağırın.

```
LONG SetGUIDValue(LPCTSTR pszValueName, REFGUID guidValue) throw();
```

### <a name="parameters"></a>Parametreler

*pszValueName*<br/>
Ayarlanacak değerin adını içeren bir dize işaretçisi. Bu ada sahip bir değer zaten yoksa, yöntemi anahtara ekler.

*GUIDDeğeri*<br/>
Belirtilen değer adıyla depolanacak GUID 'ye başvuru.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, dönüş değeri ERROR_SUCCESS olur. Yöntem başarısız olursa, dönüş değeri, WINERROR 'da tanımlanan sıfır dışı bir hata kodudur. Olsun.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, kullanımını `CRegKey::SetStringValue` sağlar ve [StringFromGUID2](/windows/desktop/api/combaseapi/nf-combaseapi-stringfromguid2)kullanarak GUID 'yi bir dizeye dönüştürür.

##  <a name="setkeyvalue"></a>CRegKey:: SetKeyValue

Belirtilen bir anahtarın belirtilen bir değer alanındaki verileri depolamak için bu yöntemi çağırın.

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
Depolanacak verileri belirtir. Bu parametre NULL olmayan bir değer olmalıdır.

*lpszValueName*<br/>
Ayarlanacak değer alanını belirtir. Bu ada sahip bir değer alanı anahtarda zaten yoksa, eklenir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, ERROR_SUCCESS döndürür; Aksi halde, WINERROR 'da tanımlanmış sıfır olmayan bir hata kodu. Olsun.

### <a name="remarks"></a>Açıklamalar

*LpszKeyName* anahtarını oluşturmak veya açmak ve *lpszValue* verilerini *lpszValueName* value alanına depolamak için bu yöntemi çağırın.

##  <a name="setkeysecurity"></a>CRegKey:: SetKeySecurity

Kayıt defteri anahtarının güvenliğini ayarlamak için bu yöntemi çağırın.

```
LONG SetKeySecurity(SECURITY_INFORMATION si, PSECURITY_DESCRIPTOR psd) throw();
```

### <a name="parameters"></a>Parametreler

*ortası*<br/>
Ayarlanacak güvenlik tanımlayıcısının bileşenlerini belirtir. Değer aşağıdaki değerlerin bir birleşimi olabilir:

|Değer|Açıklama|
|-----------|-------------|
|DACL_SECURITY_INFORMATION|Anahtarın isteğe bağlı erişim denetimi listesini (DACL) ayarlar. Anahtarın WRITE_DAC erişimi olmalıdır veya çağırma işleminin nesnenin sahibi olması gerekir.|
|GROUP_SECURITY_INFORMATION|Anahtarın birincil grup güvenlik tanımlayıcısını (SID) ayarlar. Anahtarın WRITE_OWNER erişimi olmalıdır veya çağırma işleminin nesnenin sahibi olması gerekir.|
|OWNER_SECURITY_INFORMATION|Anahtarın sahip SID 'sini ayarlar. Anahtarın WRITE_OWNER erişimi olmalıdır ya da çağıran işlem, nesnenin sahibi olmalı veya SE_TAKE_OWNERSHIP_NAME ayrıcalığının etkin olmalıdır.|
|SACL_SECURITY_INFORMATION|Anahtarın sistem erişim denetimi listesini (SACL) ayarlar. Anahtarın ACCESS_SYSTEM_SECURITY erişimi olmalıdır. Bu erişimi almanın doğru yolu, çağıranın geçerli erişim belirtecindeki SE_SECURITY_NAME [ayrıcalığını](/windows/desktop/secauthz/privileges) ETKINLEŞTIRMEK, ACCESS_SYSTEM_SECURITY Access için tanıtıcıyı açmak ve ardından ayrıcalığını devre dışı bırakmanız olur.|

*PSD*<br/>
Belirtilen anahtar için ayarlanacak güvenlik özniteliklerini belirten bir [SECURITY_DESCRIPTOR](/windows/desktop/api/winnt/ns-winnt-security_descriptor) yapısına yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, dönüş değeri ERROR_SUCCESS olur. Yöntem başarısız olursa, dönüş değeri, WINERROR 'da tanımlanan sıfır dışı bir hata kodudur. Olsun.

### <a name="remarks"></a>Açıklamalar

Anahtarın güvenlik özniteliklerini ayarlar. Daha fazla ayrıntı için bkz. [RegSetKeySecurity](/windows/desktop/api/winreg/nf-winreg-regsetkeysecurity) .

##  <a name="setmultistringvalue"></a>CRegKey:: SetMultiStringValue

Kayıt defteri anahtarının MultiString değerini ayarlamak için bu yöntemi çağırın.

```
LONG SetMultiStringValue(LPCTSTR pszValueName, LPCTSTR pszValue) throw();
```

### <a name="parameters"></a>Parametreler

*pszValueName*<br/>
Ayarlanacak değerin adını içeren bir dize işaretçisi. Bu ada sahip bir değer zaten yoksa, yöntemi anahtara ekler.

*pszValue*<br/>
Belirtilen değer adıyla depolanacak çok dizeli verilerin işaretçisi. Çoklu dize, null ile sonlandırılmış dizelerin dizileridir ve iki null karakterle sonlandırılır.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, dönüş değeri ERROR_SUCCESS olur. Yöntem başarısız olursa, dönüş değeri, WINERROR 'da tanımlanan sıfır dışı bir hata kodudur. Olsun.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, kayıt defterine değeri yazmak için [RegSetValueEx](/windows/desktop/api/winreg/nf-winreg-regsetvalueexa) kullanır.

##  <a name="setqwordvalue"></a>CRegKey:: SetQWORDValue

Kayıt defteri anahtarının QWORD değerini ayarlamak için bu yöntemi çağırın.

```
LONG SetQWORDValue(LPCTSTR pszValueName, ULONGLONG qwValue) throw();
```

### <a name="parameters"></a>Parametreler

*pszValueName*<br/>
Ayarlanacak değerin adını içeren bir dize işaretçisi. Bu ada sahip bir değer zaten yoksa, yöntemi anahtara ekler.

*qwValue*<br/>
Belirtilen değer adıyla depolanacak olan QWORD verileri.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, dönüş değeri ERROR_SUCCESS olur. Yöntem başarısız olursa, dönüş değeri, WINERROR 'da tanımlanan sıfır dışı bir hata kodudur. Olsun.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, kayıt defterine değeri yazmak için [RegSetValueEx](/windows/desktop/api/winreg/nf-winreg-regsetvalueexa) kullanır.

##  <a name="setstringvalue"></a>CRegKey:: SetStringValue

Kayıt defteri anahtarının dize değerini ayarlamak için bu yöntemi çağırın.

```
LONG SetStringValue(
    LPCTSTR pszValueName,
    LPCTSTR pszValue,
    DWORD dwType = REG_SZ) throw();
```

### <a name="parameters"></a>Parametreler

*pszValueName*<br/>
Ayarlanacak değerin adını içeren bir dize işaretçisi. Bu ada sahip bir değer zaten yoksa, yöntemi anahtara ekler.

*pszValue*<br/>
Belirtilen değer adıyla depolanacak dize verileri işaretçisi.

*dwType*<br/>
Kayıt defterine yazılacak dizenin türü: REG_SZ (varsayılan) ya da REG_EXPAND_SZ (çok dizeli dizeler için).

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, dönüş değeri ERROR_SUCCESS olur. Yöntem başarısız olursa, dönüş değeri, WINERROR 'da tanımlanan sıfır dışı bir hata kodudur. Olsun.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, kayıt defterine değeri yazmak için [RegSetValueEx](/windows/desktop/api/winreg/nf-winreg-regsetvalueexa) kullanır.

##  <a name="setvalue"></a>CRegKey:: SetValue

[M_hKey](#m_hkey)'in belirtilen değer alanına veri depolamak için bu yöntemi çağırın. Bu yöntemin önceki sürümleri artık desteklenmemektedir ve ATL_DEPRECATED olarak işaretlenir.

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
Ayarlanacak değerin adını içeren bir dize işaretçisi. Bu ada sahip bir değer anahtarda zaten yoksa, yöntemi anahtara ekler. *PszValueName* null veya boş bir dize ise, "" yöntemi, anahtarın adlandırılmamış veya varsayılan değeri için türü ve verileri ayarlar.

*dwType*<br/>
*PValue* parametresinin işaret ettiği veri türünü gösteren bir kodu belirtir.

*pValue*<br/>
Belirtilen değer adıyla depolanacak verileri içeren bir arabelleğin işaretçisi.

*nBytes*<br/>
*PValue* parametresi tarafından işaret edilen bilgilerin boyutunu bayt cinsinden belirtir. Veriler REG_SZ, REG_EXPAND_SZ veya REG_MULTI_SZ türünde ise, *nBytes* Sonlandırıcı null karakterinin boyutunu içermelidir.

*hKeyParent*<br/>
Açık bir anahtarın tanıtıcısı.

*lpszKeyName*<br/>
Oluşturulacak veya açılacak bir anahtarın adını belirtir. Bu ad, *hKeyParent*'nin bir alt anahtarı olmalıdır.

*lpszValue*<br/>
Depolanacak verileri belirtir. Bu parametre NULL olmayan bir değer olmalıdır.

*lpszValueName*<br/>
Ayarlanacak değer alanını belirtir. Bu ada sahip bir değer alanı anahtarda zaten yoksa, eklenir.

*dwValue*<br/>
Depolanacak verileri belirtir.

*bMulti*<br/>
Yanlışsa, dizenin REG_SZ türünde olduğunu gösterir. True ise, dizenin REG_MULTI_SZ türünde çok dizeli olduğunu gösterir.

*nValueLen*<br/>
*BMulti* true Ise *Nvaluelen* , *lpszValue* dizesinin karakter cinsinden uzunluğudur. *BMulti* yanlış ise,-1 değeri yöntemin uzunluğu otomatik olarak hesaplayacağını belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, ERROR_SUCCESS döndürür; Aksi halde, WINERROR 'da tanımlanmış sıfır olmayan bir hata kodu. Olsun.

### <a name="remarks"></a>Açıklamalar

Öğesinin `SetValue` iki orijinal sürümü ATL_DEPRECATED olarak işaretlenir ve artık kullanılmamalıdır. Bu formlar kullanılıyorsa derleyici bir uyarı oluşturur.

Üçüncü yöntem [RegSetValueEx](/windows/desktop/api/winreg/nf-winreg-regsetvalueexa)çağırır.

## <a name="see-also"></a>Ayrıca bkz.

[DCOM örneği](../../overview/visual-cpp-samples.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
