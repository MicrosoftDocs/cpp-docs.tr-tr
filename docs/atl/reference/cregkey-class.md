---
description: 'Daha fazla bilgi edinin: CRegKey sınıfı'
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
ms.openlocfilehash: f95a4f165d2d2d3d964c74c0c2c07db7a03e6fb3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97140874"
---
# <a name="cregkey-class"></a>CRegKey sınıfı

Bu sınıf, sistem kayıt defterindeki girdileri işlemek için yöntemler sağlar.

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Syntax

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
|[CRegKey:: Attach](#attach)|`CRegKey` [M_hKey](#m_hkey) üye tanıtıcısını olarak AYARLAYARAK nesnesine bir HKEY eklemek için bu yöntemi çağırın `hKey` .|
|[CRegKey:: Close](#close)|[M_hKey](#m_hkey) üye tanıtıcısını serbest BıRAKMAK ve null olarak ayarlamak için bu yöntemi çağırın.|
|[CRegKey:: Create](#create)|Bir alt anahtarı olarak mevcut değilse, belirtilen anahtarı oluşturmak için bu yöntemi çağırın `hKeyParent` .|
|[CRegKey::D Eletealtanahtar](#deletesubkey)|Belirtilen anahtarı kayıt defterinden kaldırmak için bu yöntemi çağırın.|
|[CRegKey::D eleteValue](#deletevalue)|[M_hKey](#m_hkey)bir değer alanı kaldırmak için bu yöntemi çağırın.|
|[CRegKey::D etach](#detach)|[M_hKey](#m_hkey) üye tanıtıcısını `CRegKey` NESNEDEN ayırmak ve null olarak ayarlamak için bu yöntemi çağırın `m_hKey` .|
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
|[CRegKey:: QueryValue](#queryvalue)|[M_hKey](#m_hkey)belirtilen değer alanı için verileri almak üzere bu yöntemi çağırın. Bu yöntemin önceki sürümleri artık desteklenmemektedir ve ATL_DEPRECATED olarak işaretlenir.|
|[CRegKey:: RecurseDeleteKey](#recursedeletekey)|Belirtilen anahtarı kayıt defterinden kaldırmak ve tüm alt anahtarları açıkça kaldırmak için bu yöntemi çağırın.|
|[CRegKey:: SetBinaryValue](#setbinaryvalue)|Kayıt defteri anahtarının ikili değerini ayarlamak için bu yöntemi çağırın.|
|[CRegKey:: SetDWORDValue](#setdwordvalue)|Kayıt defteri anahtarının DWORD değerini ayarlamak için bu yöntemi çağırın.|
|[CRegKey:: Setguiddeğeri](#setguidvalue)|Kayıt defteri anahtarının GUID değerini ayarlamak için bu yöntemi çağırın.|
|[CRegKey:: SetKeySecurity](#setkeysecurity)|Kayıt defteri anahtarının güvenliğini ayarlamak için bu yöntemi çağırın.|
|[CRegKey:: SetKeyValue](#setkeyvalue)|Belirtilen bir anahtarın belirtilen bir değer alanındaki verileri depolamak için bu yöntemi çağırın.|
|[CRegKey:: SetMultiStringValue](#setmultistringvalue)|Kayıt defteri anahtarının MultiString değerini ayarlamak için bu yöntemi çağırın.|
|[CRegKey:: SetQWORDValue](#setqwordvalue)|Kayıt defteri anahtarının QWORD değerini ayarlamak için bu yöntemi çağırın.|
|[CRegKey:: SetStringValue](#setstringvalue)|Kayıt defteri anahtarının dize değerini ayarlamak için bu yöntemi çağırın.|
|[CRegKey:: SetValue](#setvalue)|[M_hKey](#m_hkey)belirtilen değer alanındaki verileri depolamak için bu yöntemi çağırın. Bu yöntemin önceki sürümleri artık desteklenmemektedir ve ATL_DEPRECATED olarak işaretlenir.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CRegKey:: operator HKEY](#operator_hkey)|Bir `CRegKey` nesneyi BIR HKEY öğesine dönüştürür.|
|[CRegKey:: operator =](#operator_eq)|Atama işleci.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CRegKey:: m_hKey](#m_hkey)|Nesnesiyle ilişkili kayıt defteri anahtarının bir işleyicisini içerir `CRegKey` .|
|[CRegKey:: m_pTM](#m_ptm)|Nesne işaretçisi `CAtlTransactionManager`|

## <a name="remarks"></a>Açıklamalar

`CRegKey` Sistem kayıt defterinde anahtar ve değer oluşturmak ve silmek için yöntemler sağlar. Kayıt defteri, yazılım sürüm numaraları, yüklü donanımın mantıksal-fiziksek eşlemeleri ve COM nesneleri gibi sistem bileşenleri için yüklemeye özgü bir tanımlar kümesi içerir.

`CRegKey` belirli bir makine için sistem kayıt defterine bir programlama arabirimi sağlar. Örneğin, belirli bir kayıt defteri anahtarını açmak için çağrısı yapın `CRegKey::Open` . Bir veri değerini almak veya değiştirmek için `CRegKey::QueryValue` `CRegKey::SetValue` sırasıyla veya ' ı çağırın. Bir anahtarı kapatmak için çağrısı yapın `CRegKey::Close` .

Bir anahtarı kapattığınızda, kayıt defteri verileri sabit diske yazılır (temizlenir). Bu işlem birkaç saniye sürebilir. Uygulamanızın kayıt defteri verilerini sabit diske açıkça yazması gerekiyorsa, [RegFlushKey](/windows/win32/api/winreg/nf-winreg-regflushkey) Win32 işlevini çağırabilirsiniz. Ancak, `RegFlushKey` birçok sistem kaynağını kullanır ve yalnızca kesinlikle gerekli olduğunda çağrılmalıdır.

> [!IMPORTANT]
> Çağıranın bir kayıt defteri konumu belirtmesini sağlayan yöntemlerin, güvenilir olmayan verileri okuma olasılığı vardır. [RegQueryValueEx](/windows/win32/api/winreg/nf-winreg-regqueryvalueexw) 'yi kullanan Yöntemler, bu işlevin null olarak sonlandırılmış dizeleri açıkça işlemediğini dikkate almalıdır. Her iki koşul de çağıran kod tarafından denetlenmelidir.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase. h

## <a name="cregkeyattach"></a><a name="attach"></a> CRegKey:: Attach

`CRegKey` [M_hKey](#m_hkey) üye tanıtıcısını *HKEY* olarak ayarlayarak nesnesine bir HKEY eklemek için bu yöntemi çağırın.

```cpp
void Attach(HKEY hKey) throw();
```

### <a name="parameters"></a>Parametreler

*hKey*<br/>
Kayıt defteri anahtarının tanıtıcısı.

### <a name="remarks"></a>Açıklamalar

`Attach``m_hKey`null değilse onay olur.

## <a name="cregkeyclose"></a><a name="close"></a> CRegKey:: Close

[M_hKey](#m_hkey) üye tanıtıcısını serbest BıRAKMAK ve null olarak ayarlamak için bu yöntemi çağırın.

```
LONG Close() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa ERROR_SUCCESS döndürür; Aksi takdirde bir hata değeri döndürür.

## <a name="cregkeycreate"></a><a name="create"></a> CRegKey:: Create

Bir *hKeyParent* alt anahtarı olarak yoksa, belirtilen anahtarı oluşturmak için bu yöntemi çağırın.

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
Oluşturulacak veya açılacak anahtarın sınıfını belirtir. Varsayılan değer REG_NONE.

*dwOptions*<br/>
Anahtar seçenekleri. Varsayılan değer REG_OPTION_NON_VOLATILE. Olası değerler ve açıklamaların bir listesi için, bkz. [RegCreateKeyEx](/windows/win32/api/winreg/nf-winreg-regcreatekeyexw) in Windows SDK.

*samDesired*<br/>
Anahtar için güvenlik erişimi. Varsayılan değer KEY_READ &#124; KEY_WRITE. Olası değerler ve açıklamaların bir listesi için bkz `RegCreateKeyEx` ..

*lpSecAttr*<br/>
Anahtar tanıtıcısının bir alt işlem tarafından devralınıp alınmayacağını belirten [SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\)) yapısına yönelik bir işaretçi. Varsayılan olarak, bu parametre NULL (tanıtıcı devralınamaz anlamına gelir).

*lpdwDisposition*<br/>
dışı NULL olmayan, REG_CREATED_NEW_KEY (anahtar yoksa ve oluşturulduysa) veya REG_OPENED_EXISTING_KEY (anahtar varsa ve açılırsa) alır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, ERROR_SUCCESS döndürür ve anahtarı açar. Yöntem başarısız olursa, dönüş değeri WINERROR. H içinde tanımlanan sıfır dışı bir hata kodudur.

### <a name="remarks"></a>Açıklamalar

`Create`[m_hKey](#m_hkey) üyesini bu anahtarın tanıtıcısına ayarlar.

## <a name="cregkeycregkey"></a><a name="cregkey"></a> CRegKey:: CRegKey

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

Yeni bir `CRegKey` nesne oluşturur. Nesne varolan bir `CRegKey` nesneden veya bir işleyicinizden bir kayıt defteri anahtarına oluşturulabilir.

## <a name="cregkeycregkey"></a><a name="dtor"></a> CRegKey:: ~ CRegKey

Yok edicisi.

```
~CRegKey() throw();
```

### <a name="remarks"></a>Açıklamalar

Yıkıcı yayınlar `m_hKey` .

## <a name="cregkeydeletesubkey"></a><a name="deletesubkey"></a> CRegKey::D Eletealtanahtar

Belirtilen anahtarı kayıt defterinden kaldırmak için bu yöntemi çağırın.

```
LONG DeleteSubKey(LPCTSTR lpszSubKey) throw();
```

### <a name="parameters"></a>Parametreler

*lpszSubKey*<br/>
Silinecek anahtarın adını belirtir. Bu ad [m_hKey](#m_hkey)bir alt anahtar olmalıdır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa ERROR_SUCCESS döndürür. Yöntem başarısız olursa, dönüş değeri WINERROR. H içinde tanımlanan sıfır dışı bir hata kodudur.

### <a name="remarks"></a>Açıklamalar

`DeleteSubKey` yalnızca alt anahtarı olmayan bir anahtar silinebilir. Anahtarın alt anahtarları varsa, bunun yerine [RecurseDeleteKey](#recursedeletekey) çağırın.

## <a name="cregkeydeletevalue"></a><a name="deletevalue"></a> CRegKey::D eleteValue

[M_hKey](#m_hkey)bir değer alanı kaldırmak için bu yöntemi çağırın.

```
LONG DeleteValue(LPCTSTR lpszValue) throw();
```

### <a name="parameters"></a>Parametreler

*lpszValue*<br/>
Kaldırılacak değer alanını belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa ERROR_SUCCESS döndürür. Yöntem başarısız olursa, dönüş değeri WINERROR. H içinde tanımlanan sıfır dışı bir hata kodudur.

## <a name="cregkeydetach"></a><a name="detach"></a> CRegKey::D etach

[M_hKey](#m_hkey) üye tanıtıcısını `CRegKey` NESNEDEN ayırmak ve null olarak ayarlamak için bu yöntemi çağırın `m_hKey` .

```
HKEY Detach() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Nesneyle ilişkili HKEY `CRegKey` .

## <a name="cregkeyenumkey"></a><a name="enumkey"></a> CRegKey:: EnumKey

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

Yöntem başarılı olursa, dönüş değeri ERROR_SUCCESS olur. Yöntem başarısız olursa, dönüş değeri WINERROR. H içinde tanımlanan sıfır dışı bir hata kodudur.

### <a name="remarks"></a>Açıklamalar

Alt anahtarları numaralandırmak için, `CRegKey::EnumKey` sıfır diziniyle çağırın. Dizin değerini artırın ve Yöntem ERROR_NO_MORE_ITEMS dönene kadar tekrarlayın. Daha fazla bilgi için Windows SDK [RegEnumKeyEx](/windows/win32/api/winreg/nf-winreg-regenumkeyexw) bakın.

## <a name="cregkeyflush"></a><a name="flush"></a> CRegKey:: Flush

Açık kayıt defteri anahtarının tüm özniteliklerini kayıt defterine yazmak için bu yöntemi çağırın.

```
LONG Flush() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, dönüş değeri ERROR_SUCCESS olur. Yöntem başarısız olursa, dönüş değeri WINERROR. H içinde tanımlanan sıfır dışı bir hata kodudur.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için Windows SDK bkz. [RegEnumFlush](/windows/win32/api/winreg/nf-winreg-regflushkey) .

## <a name="cregkeygetkeysecurity"></a><a name="getkeysecurity"></a> CRegKey:: GetKeySecurity

Açık kayıt defteri anahtarını koruyan güvenlik tanımlayıcısının bir kopyasını almak için bu yöntemi çağırın.

```
LONG GetKeySecurity(
    SECURITY_INFORMATION si,
    PSECURITY_DESCRIPTOR psd,
    LPDWORD pnBytes) throw();
```

### <a name="parameters"></a>Parametreler

*ortası*<br/>
İstenen güvenlik bilgilerini gösteren [SECURITY_INFORMATION](/windows/win32/SecAuthZ/security-information) değeri.

*PSD*<br/>
İstenen güvenlik tanımlayıcısının kopyasını alan bir arabelleğin işaretçisi.

*pnBytes*<br/>
*PSD* tarafından işaret edilen arabelleğin bayt cinsinden boyutu.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, dönüş değeri ERROR_SUCCESS olur. Yöntem başarısız olursa, dönüş değeri bir sıfır dışı hata kodu, WINERROR. H içinde tanımlanır.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [RegGetKeySecurity](/windows/win32/api/winreg/nf-winreg-reggetkeysecurity).

## <a name="cregkeym_hkey"></a><a name="m_hkey"></a> CRegKey:: m_hKey

Nesnesiyle ilişkili kayıt defteri anahtarının bir işleyicisini içerir `CRegKey` .

```
HKEY m_hKey;
```

## <a name="cregkeym_ptm"></a><a name="m_ptm"></a> CRegKey:: m_pTM

Bir nesne işaretçisi `CAtlTransactionManager` .

```
CAtlTransactionManager* m_pTM;
```

### <a name="remarks"></a>Açıklamalar

## <a name="cregkeynotifychangekeyvalue"></a><a name="notifychangekeyvalue"></a> CRegKey:: NotifyChangeKeyValue

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

|Değer|Anlamı|
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

Yöntem başarılı olursa, dönüş değeri ERROR_SUCCESS olur. Yöntem başarısız olursa, dönüş değeri WINERROR. H içinde tanımlanan sıfır dışı bir hata kodudur.

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
> Bu yöntem, belirtilen anahtar silinirse çağrıyı yapana bildirmez.

Daha fazla bilgi ve örnek program için bkz. [RegNotifyChangeKeyValue](/windows/win32/api/winreg/nf-winreg-regnotifychangekeyvalue).

## <a name="cregkeyopen"></a><a name="open"></a> CRegKey:: Open

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
Anahtar için güvenlik erişimi. Varsayılan değer KEY_ALL_ACCESS. Olası değerler ve açıklamaların bir listesi için, bkz. [RegCreateKeyEx](/windows/win32/api/winreg/nf-winreg-regcreatekeyexw) in Windows SDK.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa ERROR_SUCCESS döndürür; Aksi halde, WINERROR. H içinde sıfır olmayan bir hata değeri tanımlandı.

### <a name="remarks"></a>Açıklamalar

*LpszKeyName* parametresi null veya boş bir dizeye işaret ediyorsa, `Open` *hKeyParent* tarafından tanımlanan anahtarın yeni bir işleyicisini açar, ancak daha önce açılmış bir tanıtıcıyı kapatmaz.

[CRegKey:: Create](#create)' in aksine, `Open` mevcut değilse belirtilen anahtarı oluşturmaz.

## <a name="cregkeyoperator-hkey"></a><a name="operator_hkey"></a> CRegKey:: operator HKEY

Bir `CRegKey` nesneyi BIR HKEY öğesine dönüştürür.

```
operator HKEY() const throw();
```

## <a name="cregkeyoperator-"></a><a name="operator_eq"></a> CRegKey:: operator =

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

Bu işleç, *anahtarı* geçerli nesnesinden ayırır ve `CRegKey` bunun yerine nesnesine atar.

## <a name="cregkeyquerybinaryvalue"></a><a name="querybinaryvalue"></a> CRegKey:: QueryBinaryValue

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

Yöntem başarılı olursa ERROR_SUCCESS döndürülür. Yöntem bir değeri okuyamazsa, WINERROR. H içinde tanımlanan sıfır olmayan bir hata kodu döndürür. Başvurulan veriler REG_BINARY türünde değilse, ERROR_INVALID_DATA döndürülür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, ' nin kullanımını sağlar `RegQueryValueEx` ve doğru türde verilerin döndürüldüğünü onaylar. Daha fazla ayrıntı için bkz. [RegQueryValueEx](/windows/win32/api/winreg/nf-winreg-regqueryvalueexw) .

> [!IMPORTANT]
> Bu yöntem, çağıranın hiçbir kayıt defteri konumu belirtmesini sağlar. Bu, güvenilmez olmayan verileri okuyabilir. Ayrıca, bu yöntem tarafından kullanılan [RegQueryValueEx](/windows/win32/api/winreg/nf-winreg-regqueryvalueexw) IşLEVI, null olarak sonlandırılmış dizeleri açıkça işlemez. Her iki koşul de çağıran kod tarafından denetlenmelidir.

## <a name="cregkeyquerydwordvalue"></a><a name="querydwordvalue"></a> CRegKey:: QueryDWORDValue

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

Yöntem başarılı olursa ERROR_SUCCESS döndürülür. Yöntem bir değeri okuyamazsa, WINERROR. H içinde tanımlanan sıfır olmayan bir hata kodu döndürür. Başvurulan veriler REG_DWORD türünde değilse, ERROR_INVALID_DATA döndürülür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, ' nin kullanımını sağlar `RegQueryValueEx` ve doğru türde verilerin döndürüldüğünü onaylar. Daha fazla ayrıntı için bkz. [RegQueryValueEx](/windows/win32/api/winreg/nf-winreg-regqueryvalueexw) .

> [!IMPORTANT]
> Bu yöntem, çağıranın hiçbir kayıt defteri konumu belirtmesini sağlar. Bu, güvenilmez olmayan verileri okuyabilir. Ayrıca, bu yöntem tarafından kullanılan [RegQueryValueEx](/windows/win32/api/winreg/nf-winreg-regqueryvalueexw) IşLEVI, null olarak sonlandırılmış dizeleri açıkça işlemez. Her iki koşul de çağıran kod tarafından denetlenmelidir.

## <a name="cregkeyqueryguidvalue"></a><a name="queryguidvalue"></a> CRegKey:: Queryguıddeğeri

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

Yöntem başarılı olursa ERROR_SUCCESS döndürülür. Yöntem bir değeri okuyamazsa, WINERROR. H içinde tanımlanan sıfır olmayan bir hata kodu döndürür. Başvurulan veriler geçerli bir GUID değilse, ERROR_INVALID_DATA döndürülür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, ' nin kullanımını sağlar `CRegKey::QueryStringValue` ve [Clsidfromstring](/windows/win32/api/combaseapi/nf-combaseapi-clsidfromstring)kullanarak dizeyi bir GUID 'ye dönüştürür.

> [!IMPORTANT]
> Bu yöntem, çağıranın hiçbir kayıt defteri konumu belirtmesini sağlar. Bu, güvenilmez olmayan verileri okuyabilir.

## <a name="cregkeyquerymultistringvalue"></a><a name="querymultistringvalue"></a> CRegKey:: QueryMultiStringValue

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
*PszValue* tarafından işaret edilen arabelleğin, TCHARs cinsinden boyutu. Yöntem döndürüldüğünde, *pnChar* , bir Sonlandırıcı null karakteri de dahil olmak üzere çok dizeli alınan, TCHARs cinsinden boyutu içerir.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa ERROR_SUCCESS döndürülür. Yöntem bir değeri okuyamazsa, WINERROR. H içinde tanımlanan sıfır olmayan bir hata kodu döndürür. Başvurulan veriler REG_MULTI_SZ türünde değilse, ERROR_INVALID_DATA döndürülür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, ' nin kullanımını sağlar `RegQueryValueEx` ve doğru türde verilerin döndürüldüğünü onaylar. Daha fazla ayrıntı için bkz. [RegQueryValueEx](/windows/win32/api/winreg/nf-winreg-regqueryvalueexw) .

> [!IMPORTANT]
> Bu yöntem, çağıranın hiçbir kayıt defteri konumu belirtmesini sağlar. Bu, güvenilmez olmayan verileri okuyabilir. Ayrıca, bu yöntem tarafından kullanılan [RegQueryValueEx](/windows/win32/api/winreg/nf-winreg-regqueryvalueexw) IşLEVI, null olarak sonlandırılmış dizeleri açıkça işlemez. Her iki koşul de çağıran kod tarafından denetlenmelidir.

## <a name="cregkeyqueryqwordvalue"></a><a name="queryqwordvalue"></a> CRegKey:: QueryQWORDValue

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

Yöntem başarılı olursa ERROR_SUCCESS döndürülür. Yöntem bir değeri okuyamazsa, WINERROR. H içinde tanımlanan sıfır olmayan bir hata kodu döndürür. Başvurulan veriler REG_QWORD türünde değilse, ERROR_INVALID_DATA döndürülür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, ' nin kullanımını sağlar `RegQueryValueEx` ve doğru türde verilerin döndürüldüğünü onaylar. Daha fazla ayrıntı için bkz. [RegQueryValueEx](/windows/win32/api/winreg/nf-winreg-regqueryvalueexw) .

> [!IMPORTANT]
> Bu yöntem, çağıranın hiçbir kayıt defteri konumu belirtmesini sağlar. Bu, güvenilmez olmayan verileri okuyabilir. Ayrıca, bu yöntem tarafından kullanılan [RegQueryValueEx](/windows/win32/api/winreg/nf-winreg-regqueryvalueexw) IşLEVI, null olarak sonlandırılmış dizeleri açıkça işlemez. Her iki koşul de çağıran kod tarafından denetlenmelidir.

## <a name="cregkeyquerystringvalue"></a><a name="querystringvalue"></a> CRegKey:: QueryStringValue

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
*PszValue* tarafından işaret edilen arabelleğin, TCHARs cinsinden boyutu. Yöntemi döndürüldüğünde, *pnChar* , bir Sonlandırıcı null karakteri de dahil olmak üzere, alınan dizenin TCHARs cinsinden boyutunu içerir.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa ERROR_SUCCESS döndürülür. Yöntem bir değeri okuyamazsa, WINERROR. H içinde tanımlanan sıfır olmayan bir hata kodu döndürür. Başvurulan veriler REG_SZ türünde değilse, ERROR_INVALID_DATA döndürülür. Yöntem ERROR_MORE_DATA döndürürse, *pnChar* 'lar, gerekli arabellek boyutunu bayt cinsinden değil, sıfır olarak eşittir.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, ' nin kullanımını sağlar `RegQueryValueEx` ve doğru türde verilerin döndürüldüğünü onaylar. Daha fazla ayrıntı için bkz. [RegQueryValueEx](/windows/win32/api/winreg/nf-winreg-regqueryvalueexw) .

> [!IMPORTANT]
> Bu yöntem, çağıranın hiçbir kayıt defteri konumu belirtmesini sağlar. Bu, güvenilmez olmayan verileri okuyabilir. Ayrıca, bu yöntem tarafından kullanılan [RegQueryValueEx](/windows/win32/api/winreg/nf-winreg-regqueryvalueexw) IşLEVI, null olarak sonlandırılmış dizeleri açıkça işlemez. Her iki koşul de çağıran kod tarafından denetlenmelidir.

## <a name="cregkeyqueryvalue"></a><a name="queryvalue"></a> CRegKey:: QueryValue

[M_hKey](#m_hkey)belirtilen değer alanı için verileri almak üzere bu yöntemi çağırın. Bu yöntemin önceki sürümleri artık desteklenmemektedir ve ATL_DEPRECATED olarak işaretlenir.

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

Başarılı olursa ERROR_SUCCESS döndürür; Aksi halde, WINERROR. H içinde tanımlanan sıfır dışı bir hata kodu.

### <a name="remarks"></a>Açıklamalar

Öğesinin iki orijinal sürümü `QueryValue` artık desteklenmemektedir ve ATL_DEPRECATED olarak işaretlenir. Bu formlar kullanılıyorsa derleyici bir uyarı oluşturur.

Kalan Yöntem RegQueryValueEx çağırır.

> [!IMPORTANT]
> Bu yöntem, çağıranın hiçbir kayıt defteri konumu belirtmesini sağlar. Bu, güvenilmez olmayan verileri okuyabilir. Ayrıca, bu yöntem tarafından kullanılan RegQueryValueEx işlevi, NULL olarak sonlandırılmış dizeleri açıkça işlemez. Her iki koşul de çağıran kod tarafından denetlenmelidir.

## <a name="cregkeyrecursedeletekey"></a><a name="recursedeletekey"></a> CRegKey:: RecurseDeleteKey

Belirtilen anahtarı kayıt defterinden kaldırmak ve tüm alt anahtarları açıkça kaldırmak için bu yöntemi çağırın.

```
LONG RecurseDeleteKey(LPCTSTR lpszKey) throw();
```

### <a name="parameters"></a>Parametreler

*lpszKey*<br/>
Silinecek anahtarın adını belirtir. Bu ad [m_hKey](#m_hkey)bir alt anahtar olmalıdır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa ERROR_SUCCESS döndürür; Aksi halde, WINERROR. H içinde sıfır olmayan bir hata değeri tanımlandı.

### <a name="remarks"></a>Açıklamalar

Anahtarın alt anahtarları varsa, anahtarı silmek için bu yöntemi çağırmanız gerekir.

## <a name="cregkeysetbinaryvalue"></a><a name="setbinaryvalue"></a> CRegKey:: SetBinaryValue

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

Yöntem başarılı olursa, dönüş değeri ERROR_SUCCESS olur. Yöntem başarısız olursa, dönüş değeri WINERROR. H içinde tanımlanan sıfır dışı bir hata kodudur.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, kayıt defterine değeri yazmak için [RegSetValueEx](/windows/win32/api/winreg/nf-winreg-regsetvalueexw) kullanır.

## <a name="cregkeysetdwordvalue"></a><a name="setdwordvalue"></a> CRegKey:: SetDWORDValue

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

Yöntem başarılı olursa, dönüş değeri ERROR_SUCCESS olur. Yöntem başarısız olursa, dönüş değeri WINERROR. H içinde tanımlanan sıfır dışı bir hata kodudur.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, kayıt defterine değeri yazmak için [RegSetValueEx](/windows/win32/api/winreg/nf-winreg-regsetvalueexw) kullanır.

## <a name="cregkeysetguidvalue"></a><a name="setguidvalue"></a> CRegKey:: Setguiddeğeri

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

Yöntem başarılı olursa, dönüş değeri ERROR_SUCCESS olur. Yöntem başarısız olursa, dönüş değeri WINERROR. H içinde tanımlanan sıfır dışı bir hata kodudur.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, kullanımını sağlar `CRegKey::SetStringValue` ve [STRINGFROMGUID2](/windows/win32/api/combaseapi/nf-combaseapi-stringfromguid2)kullanarak GUID 'yi bir dizeye dönüştürür.

## <a name="cregkeysetkeyvalue"></a><a name="setkeyvalue"></a> CRegKey:: SetKeyValue

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

Başarılı olursa ERROR_SUCCESS döndürür; Aksi halde, WINERROR. H içinde tanımlanan sıfır dışı bir hata kodu.

### <a name="remarks"></a>Açıklamalar

*LpszKeyName* anahtarını oluşturmak veya açmak ve *lpszValue* verilerini *lpszValueName* value alanına depolamak için bu yöntemi çağırın.

## <a name="cregkeysetkeysecurity"></a><a name="setkeysecurity"></a> CRegKey:: SetKeySecurity

Kayıt defteri anahtarının güvenliğini ayarlamak için bu yöntemi çağırın.

```
LONG SetKeySecurity(SECURITY_INFORMATION si, PSECURITY_DESCRIPTOR psd) throw();
```

### <a name="parameters"></a>Parametreler

*ortası*<br/>
Ayarlanacak güvenlik tanımlayıcısının bileşenlerini belirtir. Değer aşağıdaki değerlerin bir birleşimi olabilir:

|Değer|Anlamı|
|-----------|-------------|
|DACL_SECURITY_INFORMATION|Anahtarın isteğe bağlı erişim denetimi listesini (DACL) ayarlar. Anahtarın WRITE_DAC erişimi olmalıdır veya çağırma işleminin nesnenin sahibi olması gerekir.|
|GROUP_SECURITY_INFORMATION|Anahtarın birincil grup güvenlik tanımlayıcısını (SID) ayarlar. Anahtarın WRITE_OWNER erişimi olmalıdır veya çağırma işleminin nesnenin sahibi olması gerekir.|
|OWNER_SECURITY_INFORMATION|Anahtarın sahip SID 'sini ayarlar. Anahtarın WRITE_OWNER erişimi olmalıdır veya çağırma işleminin nesnenin sahibi olması veya SE_TAKE_OWNERSHIP_NAME ayrıcalığının etkinleştirilmiş olması gerekir.|
|SACL_SECURITY_INFORMATION|Anahtarın sistem erişim denetimi listesini (SACL) ayarlar. Anahtarın ACCESS_SYSTEM_SECURITY erişimi olmalıdır. Bu erişimi almanın doğru yolu, çağıranın geçerli erişim belirtecinde SE_SECURITY_NAME [ayrıcalığını](/windows/win32/secauthz/privileges) etkinleştirmek, ACCESS_SYSTEM_SECURITY erişim tanıtıcısını açmak ve ardından ayrıcalığını devre dışı bırakmanız.|

*PSD*<br/>
Belirtilen anahtar için ayarlanacak güvenlik özniteliklerini belirten [SECURITY_DESCRIPTOR](/windows/win32/api/winnt/ns-winnt-security_descriptor) yapısına yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, dönüş değeri ERROR_SUCCESS olur. Yöntem başarısız olursa, dönüş değeri WINERROR. H içinde tanımlanan sıfır dışı bir hata kodudur.

### <a name="remarks"></a>Açıklamalar

Anahtarın güvenlik özniteliklerini ayarlar. Daha fazla ayrıntı için bkz. [RegSetKeySecurity](/windows/win32/api/winreg/nf-winreg-regsetkeysecurity) .

## <a name="cregkeysetmultistringvalue"></a><a name="setmultistringvalue"></a> CRegKey:: SetMultiStringValue

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

Yöntem başarılı olursa, dönüş değeri ERROR_SUCCESS olur. Yöntem başarısız olursa, dönüş değeri WINERROR. H içinde tanımlanan sıfır dışı bir hata kodudur.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, kayıt defterine değeri yazmak için [RegSetValueEx](/windows/win32/api/winreg/nf-winreg-regsetvalueexw) kullanır.

## <a name="cregkeysetqwordvalue"></a><a name="setqwordvalue"></a> CRegKey:: SetQWORDValue

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

Yöntem başarılı olursa, dönüş değeri ERROR_SUCCESS olur. Yöntem başarısız olursa, dönüş değeri WINERROR. H içinde tanımlanan sıfır dışı bir hata kodudur.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, kayıt defterine değeri yazmak için [RegSetValueEx](/windows/win32/api/winreg/nf-winreg-regsetvalueexw) kullanır.

## <a name="cregkeysetstringvalue"></a><a name="setstringvalue"></a> CRegKey:: SetStringValue

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
Kayıt defterine yazılacak dizenin türü: REG_SZ (varsayılan) veya REG_EXPAND_SZ (çok dizeli dizeler için).

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, dönüş değeri ERROR_SUCCESS olur. Yöntem başarısız olursa, dönüş değeri WINERROR. H içinde tanımlanan sıfır dışı bir hata kodudur.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, kayıt defterine değeri yazmak için [RegSetValueEx](/windows/win32/api/winreg/nf-winreg-regsetvalueexw) kullanır.

## <a name="cregkeysetvalue"></a><a name="setvalue"></a> CRegKey:: SetValue

[M_hKey](#m_hkey)belirtilen değer alanındaki verileri depolamak için bu yöntemi çağırın. Bu yöntemin önceki sürümleri artık desteklenmemektedir ve ATL_DEPRECATED olarak işaretlenir.

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
*PValue* parametresi tarafından işaret edilen bilgilerin boyutunu bayt cinsinden belirtir. Veriler REG_SZ, REG_EXPAND_SZ veya REG_MULTI_SZ türündedir, *nBytes* Sonlandırıcı null karakterinin boyutunu içermelidir.

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
False ise, dizenin REG_SZ türünde olduğunu gösterir. True ise, dizenin REG_MULTI_SZ türünde çok dizeli olduğunu gösterir.

*nValueLen*<br/>
*BMulti* true Ise *Nvaluelen* , *lpszValue* dizesinin karakter cinsinden uzunluğudur. *BMulti* yanlış ise,-1 değeri yöntemin uzunluğu otomatik olarak hesaplayacağını belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa ERROR_SUCCESS döndürür; Aksi halde, WINERROR. H içinde tanımlanan sıfır dışı bir hata kodu.

### <a name="remarks"></a>Açıklamalar

Öğesinin iki orijinal sürümü `SetValue` ATL_DEPRECATED olarak işaretlenir ve artık kullanılmamalıdır. Bu formlar kullanılıyorsa derleyici bir uyarı oluşturur.

Üçüncü yöntem [RegSetValueEx](/windows/win32/api/winreg/nf-winreg-regsetvalueexw)çağırır.

## <a name="see-also"></a>Ayrıca bkz.

[DCOM örneği](../../overview/visual-cpp-samples.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
