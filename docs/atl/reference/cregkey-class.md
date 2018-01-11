---
title: "CRegKey sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
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
dev_langs: C++
helpviewer_keywords:
- CRegKey class
- ATL, registry
- registry, deleting values
- registry, writing to
- registry, deleting keys
ms.assetid: 3afce82b-ba2c-4c1a-8404-dc969e1af74b
caps.latest.revision: "25"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: dffc650c54c4a50fb4b3b1fe2c22ac82501b8b45
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cregkey-class"></a>CRegKey sınıfı
Bu sınıf, sistem kayıt defteri girdileri düzenleme için yöntemleri sağlar.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class CRegKey
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CRegKey::CRegKey](#cregkey)|Oluşturucu.|  
|[CRegKey:: ~ CRegKey](#dtor)|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CRegKey::Attach](#attach)|Bir HKEY eklemek için bu yöntemi çağırın `CRegKey` ayarlayarak nesne [m_hKey](#m_hkey) üye tanıtıcıyı `hKey`.|  
|[CRegKey::Close](#close)|Serbest bırakmak için bu yöntemi çağırabilmeniz [m_hKey](#m_hkey) üye işlemek ve NULL olarak ayarlayın.|  
|[CRegKey::Create](#create)|Bir alt anahtarı olarak yoksa, belirtilen anahtar oluşturmak için bu yöntemi çağırın `hKeyParent`.|  
|[CRegKey::DeleteSubKey](#deletesubkey)|Belirtilen anahtarı kayıt defterinden kaldırmak için bu yöntemi çağırın.|  
|[CRegKey::DeleteValue](#deletevalue)|Bir değer alanından kaldırmak için bu yöntemi çağırın [m_hKey](#m_hkey).|  
|[CRegKey::Detach](#detach)|Kullanımdan çıkarmak için bu yöntemi çağırabilmeniz [m_hKey](#m_hkey) üye tanıtıcı gelen `CRegKey` nesne ve ayarlayın `m_hKey` null.|  
|[CRegKey::EnumKey](#enumkey)|Kayıt defteri anahtarı alt anahtarları numaralandırmak için bu yöntemi çağırın.|  
|[CRegKey::Flush](#flush)|Tüm açık kayıt defteri anahtarının özniteliklerini kayıt defterine yazmak için bu yöntemi çağırın.|  
|[CRegKey::GetKeySecurity](#getkeysecurity)|Kayıt defteri anahtarı koruma güvenlik tanımlayıcısı bir kopyasını almak için bu yöntemi çağırın.|  
|[CRegKey::NotifyChangeKeyValue](#notifychangekeyvalue)|Bu yöntem arayan öznitelikleri ya da kayıt defteri anahtarı içeriğini yapılan değişiklikler hakkında uyarır.|  
|[CRegKey::Open](#open)|Belirtilen anahtarı'ni açıp ayarlamak için bu yöntemi çağırın [m_hKey](#m_hkey) bu anahtarın işlenecek.|  
|[CRegKey::QueryBinaryValue](#querybinaryvalue)|Belirtilen değer adı için ikili verileri almak için bu yöntemi çağırın.|  
|[CRegKey::QueryDWORDValue](#querydwordvalue)|Belirtilen değer adı DWORD verilerini almak için bu yöntemi çağırın.|  
|[CRegKey::QueryGUIDValue](#queryguidvalue)|Belirtilen değer adı için GUID verileri almak için bu yöntemi çağırın.|  
|[CRegKey::QueryMultiStringValue](#querymultistringvalue)|Belirtilen değer adı için çok dizeli verileri almak için bu yöntemi çağırın.|  
|[CRegKey::QueryQWORDValue](#queryqwordvalue)|Belirtilen değer adı QWORD verilerini almak için bu yöntemi çağırın.|  
|[CRegKey::QueryStringValue](#querystringvalue)|Belirtilen değer adı dize verilerini almak için bu yöntemi çağırın.|  
|[CRegKey::QueryValue](#queryvalue)|Belirtilen değeri alanı için verileri almak için bu yöntemi çağırın [m_hKey](#m_hkey). Bu yöntem önceki sürümleri artık desteklenmemektedir ve olarak işaretlenmiş **ATL_DEPRECATED**.|  
|[CRegKey::RecurseDeleteKey](#recursedeletekey)|Belirtilen anahtarı kayıt defterinden kaldırın ve tüm alt açıkça kaldırmak için bu yöntemi çağırın.|  
|[CRegKey::SetBinaryValue](#setbinaryvalue)|Kayıt defteri anahtarının ikili değer ayarlamak için bu yöntemi çağırın.|  
|[CRegKey::SetDWORDValue](#setdwordvalue)|Kayıt defteri anahtarı DWORD değerini ayarlamak için bu yöntemi çağırın.|  
|[CRegKey::SetGUIDValue](#setguidvalue)|Kayıt defteri anahtarı GUID değerini ayarlamak için bu yöntemi çağırın.|  
|[CRegKey::SetKeySecurity](#setkeysecurity)|Kayıt defteri anahtarının güvenlik ayarlamak için bu yöntemi çağırın.|  
|[CRegKey::SetKeyValue](#setkeyvalue)|Belirtilen anahtar bir belirtilen değer alanına verileri depolamak için bu yöntemi çağırın.|  
|[CRegKey::SetMultiStringValue](#setmultistringvalue)|Kayıt defteri anahtarının çok dizeli değer ayarlamak için bu yöntemi çağırın.|  
|[CRegKey::SetQWORDValue](#setqwordvalue)|Kayıt defteri anahtarı QWORD değerini ayarlamak için bu yöntemi çağırın.|  
|[CRegKey::SetStringValue](#setstringvalue)|Kayıt defteri anahtarı dize değerini ayarlamak için bu yöntemi çağırın.|  
|[CRegKey::SetValue](#setvalue)|Belirtilen değer alanında verileri depolamak için bu yöntemi çağırın [m_hKey](#m_hkey). Bu yöntem önceki sürümleri artık desteklenmemektedir ve olarak işaretlenmiş **ATL_DEPRECATED**.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CRegKey::operator HKEY](#operator_hkey)|Dönüştüren bir `CRegKey` bir HKEY nesnesine.|  
|[CRegKey::operator =](#operator_eq)|Atama işleci.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CRegKey::m_hKey](#m_hkey)|İle ilişkili kayıt defteri anahtarının bir tanıtıcı içeren `CRegKey` nesnesi.|  
|[CRegKey::m_pTM](#m_ptm)|İşaretçi `CAtlTransactionManager` nesnesi|  
  
## <a name="remarks"></a>Açıklamalar  
 `CRegKey`anahtarları ve sistem kayıt defteri değerlerini oluşturma ve silme için yöntemleri sağlar. Kayıt defteri yazılım sürüm numaraları, donanımla ve COM nesnelerini mantıksal fiziksel eşleme gibi sistem bileşenleri için tanımları yükleme özgü kümesini içerir.  
  
 `CRegKey`Sistem kayıt defteri programlama arabirimine için belirli bir makine sağlar. Örneğin, belirli kayıt defteri anahtarı açılamadı çağrı `CRegKey::Open`. Almak veya bir veri değeri değiştirmek için arama `CRegKey::QueryValue` veya `CRegKey::SetValue`sırasıyla. Bir anahtar kapatmak için arama `CRegKey::Close`.  
  
 Bir anahtar kapattığınızda, kayıt defteri verilerini (temizlenmiş) sabit diske yazılır. Bu işlem birkaç saniye sürebilir. Uygulamanız için sabit disk açıkça kayıt defteri verilerini yazmalısınız durumunda arayabileceğiniz [RegFlushKey](http://msdn.microsoft.com/library/windows/desktop/ms724867) Win32 işlevi. Ancak, **RegFlushKey** birçok sistem kaynaklarını kullanır ve yalnızca kesinlikle gerekli olduğunda çağrılmalıdır.  
  
> [!IMPORTANT]
>  Kayıt defteri konumu belirtmek arayan izin herhangi bir yöntem güvenilemez verileri okumak için potansiyeline sahiptir. Olun yöntemleri kullanımını [RegQueryValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724911) bu işlev boş olarak sonlandırılmış olan dizeleri açıkça işlemiyor dikkate almanız gerekir. Her iki koşul için çağrıyı yapan kod tarafından denetlenmelidir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlbase.h  
  
##  <a name="attach"></a>CRegKey::Attach  
 Bir HKEY eklemek için bu yöntemi çağırın `CRegKey` ayarlayarak nesne [m_hKey](#m_hkey) üye tanıtıcıyı `hKey`.  
  
```
void Attach(HKEY hKey) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `hKey`  
 Bir kayıt defteri anahtarı işleci.  
  
### <a name="remarks"></a>Açıklamalar  
 **Attach** varsa onay `m_hKey` NULL olmayan bir değer.  
  
##  <a name="close"></a>CRegKey::Close  
 Serbest bırakmak için bu yöntemi çağırabilmeniz [m_hKey](#m_hkey) üye işlemek ve NULL olarak ayarlayın.  
  
```
LONG Close() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, ERROR_SUCCESS döndürür; Aksi takdirde bir hata değeri döndürür.  
  
##  <a name="create"></a>CRegKey::Create  
 Bir alt anahtarı olarak yoksa, belirtilen anahtar oluşturmak için bu yöntemi çağırın `hKeyParent`.  
  
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
 `hKeyParent`  
 Açık bir anahtarın tanımlayıcısı.  
  
 `lpszKeyName`  
 Açılan veya oluşturulacak bir anahtarın adını belirtir. Bu ad, bir alt olmalıdır `hKeyParent`.  
  
 `lpszClass`  
 Açılan veya oluşturulacak anahtar sınıfı belirtir. REG_NONE varsayılan değerdir.  
  
 `dwOptions`  
 Anahtar seçenekleri. REG_OPTION_NON_VOLATILE varsayılan değerdir. Olası değerler ve açıklamaları listesi için bkz: [RegCreateKeyEx](http://msdn.microsoft.com/library/windows/desktop/ms724844) Windows SDK'sındaki.  
  
 `samDesired`  
 Anahtar güvenlik erişim. Varsayılan KEY_READ &#124;değerdir; KEY_WRITE. Olası değerler ve açıklamaları listesi için bkz: **RegCreateKeyEx**.  
  
 *lpSecAttr*  
 Bir işaretçi bir [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560) yapısı tanıtıcı anahtarının bir alt işlem tarafından devralınan olup olmadığını gösterir. Varsayılan olarak, bu parametre NULL (tanıtıcı devralınan anlamına gelir) olur.  
  
 *lpdwDisposition*  
 [out] (Anahtar vardı ve açıldı varsa) NULL olmayan, (anahtar yoktu ve oluşturuldu varsa) REG_CREATED_NEW_KEY veya REG_OPENED_EXISTING_KEY alır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, ERROR_SUCCESS döndürür ve anahtar açar. Yöntem başarısız olursa, dönüş değeri WINERROR içinde tanımlanan bir sıfır olmayan hata kodudur. H.  
  
### <a name="remarks"></a>Açıklamalar  
 **Oluşturma** ayarlar [m_hKey](#m_hkey) üye bu anahtarın işlenecek.  
  
##  <a name="cregkey"></a>CRegKey::CRegKey  
 Oluşturucu.  
  
```
CRegKey() throw();
CRegKey(CRegKey& key) throw();
explicit CRegKey(HKEY hKey) throw();
CRegKey(CAtlTransactionManager* pTM) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `key`  
 Bir başvuru bir `CRegKey` nesnesi.  
  
 `hKey`  
 Bir kayıt defteri anahtarı için bir tanıtıcı.  
  
 `pTM`  
 CAtlTransactionManager nesnesine işaretçi  
  
### <a name="remarks"></a>Açıklamalar  
 Yeni bir `CRegKey` nesnesi. Varolan bir nesneyi oluşturulabilir `CRegKey` nesnesi veya bir kayıt defteri anahtarı için bir tanıtıcı.  
  
##  <a name="dtor"></a>CRegKey:: ~ CRegKey  
 Yok Edicisi.  
  
```
~CRegKey() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Yok Edicisi sürümleri `m_hKey`.  
  
##  <a name="deletesubkey"></a>CRegKey::DeleteSubKey  
 Belirtilen anahtarı kayıt defterinden kaldırmak için bu yöntemi çağırın.  
  
```
LONG DeleteSubKey(LPCTSTR lpszSubKey) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszSubKey`  
 Silmek için anahtar adını belirtir. Bu ad, bir alt olmalıdır [m_hKey](#m_hkey).  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, ERROR_SUCCESS döndürür. Yöntem başarısız olursa, dönüş değeri WINERROR içinde tanımlanan bir sıfır olmayan hata kodudur. H.  
  
### <a name="remarks"></a>Açıklamalar  
 `DeleteSubKey`yalnızca hiçbir alt anahtarlara sahip bir anahtarı silebilirsiniz. Anahtarı alt anahtarları varsa, çağrı [RecurseDeleteKey](#recursedeletekey) yerine.  
  
##  <a name="deletevalue"></a>CRegKey::DeleteValue  
 Bir değer alanından kaldırmak için bu yöntemi çağırın [m_hKey](#m_hkey).  
  
```
LONG DeleteValue(LPCTSTR lpszValue) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszValue`  
 Kaldırmak için değer alanını belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, ERROR_SUCCESS döndürür. Yöntem başarısız olursa, dönüş değeri WINERROR içinde tanımlanan bir sıfır olmayan hata kodudur. H.  
  
##  <a name="detach"></a>CRegKey::Detach  
 Kullanımdan çıkarmak için bu yöntemi çağırabilmeniz [m_hKey](#m_hkey) üye tanıtıcı gelen `CRegKey` nesne ve ayarlayın `m_hKey` null.  
  
```
HKEY Detach() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 HKEY ilişkili `CRegKey` nesnesi.  
  
##  <a name="enumkey"></a>CRegKey::EnumKey  
 Kayıt defteri anahtarı alt anahtarları numaralandırmak için bu yöntemi çağırın.  
  
```
LONG EnumKey(  
    DWORD iIndex,
    LPTSTR pszName,
    LPDWORD pnNameLength,
    FILETIME* pftLastWriteTime = NULL) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `iIndex`  
 Alt anahtar dizini. Bu parametre için sonraki çağrılar artar ve ilk çağrı için sıfır olması gerekir  
  
 `pszName`  
 Sondaki boş karakter içeren alt anahtarı adını alan bir arabellek işaretçi. Yalnızca alt anahtar adını değil tam anahtar hiyerarşi arabellek için kopyalanır.  
  
 *pnNameLength*  
 İşaretçi TCHARs tarafından belirtilen arabellek boyutu belirten bir değişkene `pszName` parametresi. Bu boyut sonlandırma null karakter içermelidir. Yöntem döndüğünde, gösterdiği değişkeni *pnNameLength* arabellekte depolanan karakterlerin sayısını içerir. Döndürülen sayı sonlandırma null karakteri içermez.  
  
 *pftLastWriteTime*  
 İşaretçi zaman alan bir değişkene numaralandırılmış alt son için yazılmıştır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa, dönüş değeri ERROR_SUCCESS ' dir. Yöntem başarısız olursa, dönüş değeri WINERROR içinde tanımlanan bir sıfır olmayan hata kodudur. H.  
  
### <a name="remarks"></a>Açıklamalar  
 Alt anahtarları Numaralandırılacak çağrı `CRegKey::EnumKey` sıfır dizine sahip. Dizin değerini artırın ve ERROR_NO_MORE_ITEMS yöntemi dönene kadar yineleyin. Daha fazla bilgi için bkz: [RegEnumKeyEx](http://msdn.microsoft.com/library/windows/desktop/ms724862) Windows SDK'sındaki.  
  
##  <a name="flush"></a>CRegKey::Flush  
 Tüm açık kayıt defteri anahtarının özniteliklerini kayıt defterine yazmak için bu yöntemi çağırın.  
  
```
LONG Flush() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa, dönüş değeri ERROR_SUCCESS ' dir. Yöntem başarısız olursa, dönüş değeri WINERROR içinde tanımlanan bir sıfır olmayan hata kodudur. H.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [RegEnumFlush](http://msdn.microsoft.com/library/windows/desktop/ms724867) Windows SDK'sındaki.  
  
##  <a name="getkeysecurity"></a>CRegKey::GetKeySecurity  
 Kayıt defteri anahtarı koruma güvenlik tanımlayıcısı bir kopyasını almak için bu yöntemi çağırın.  
  
```
LONG GetKeySecurity(  
    SECURITY_INFORMATION si,
    PSECURITY_DESCRIPTOR psd,
    LPDWORD pnBytes) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `si`  
 [SECURITY_INFORMATION](http://msdn.microsoft.com/library/windows/desktop/aa379573) istenen güvenlik bilgilerini gösteren değer.  
  
 `psd`  
 İstenen güvenlik tanımlayıcısı kopyasını alan bir arabellek için bir işaretçi.  
  
 `pnBytes`  
 Gösterdiği arabelleğin bayt cinsinden boyutu `psd`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa, dönüş değeri ERROR_SUCCESS ' dir. Yöntem başarısız olursa, dönüş değeri sıfır olmayan hata kodu WINERROR tanımlanandır. H.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [RegGetKeySecurity](http://msdn.microsoft.com/library/windows/desktop/aa379313).  
  
##  <a name="m_hkey"></a>CRegKey::m_hKey  
 İle ilişkili kayıt defteri anahtarının bir tanıtıcı içeren `CRegKey` nesnesi.  
  
```
HKEY m_hKey;
```  
  
##  <a name="m_ptm"></a>CRegKey::m_pTM  
 İşaretçi bir `CAtlTransactionManager` nesnesi.  
  
```
CAtlTransactionManager* m_pTM;
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="notifychangekeyvalue"></a>CRegKey::NotifyChangeKeyValue  
 Bu yöntem arayan öznitelikleri ya da kayıt defteri anahtarı içeriğini yapılan değişiklikler hakkında uyarır.  
  
```
LONG NotifyChangeKeyValue(  
    BOOL bWatchSubtree,
    DWORD dwNotifyFilter,
    HANDLE hEvent,
    BOOL bAsync = TRUE) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 *bWatchSubtree*  
 Belirtilen anahtarı ve tüm alt anahtarlarını veya yalnızca belirtilen anahtarı değişiklikler raporlanıp belirten bir bayrak belirtir. Bu parametre TRUE ise, yöntem anahtar ve alt anahtarlarından yapılan değişiklikleri bildirir. Parametre FALSE ise, yöntem değişiklikler yalnızca anahtar bildirir.  
  
 *dwNotifyFilter*  
 Hangi değişikliklerin denetim bayrakları kümesi bildirilmesi belirtir. Bu parametre bir birleşimi aşağıdaki değerlerden biri olabilir:  
  
|Değer|Açıklama|  
|-----------|-------------|  
|REG_NOTIFY_CHANGE_NAME|Bir alt eklediyseniz veya çağıranın bildirin.|  
|REG_NOTIFY_CHANGE_ATTRIBUTES|Anahtar güvenlik açıklayıcı bilgisi gibi özniteliklere yapılan değişiklikleri çağıran bildirin.|  
|REG_NOTIFY_CHANGE_LAST_SET|Anahtarın değerini değişiklikler arayan bildirin. Bu, ekleme veya silme bir değer ya da var olan bir değerle değiştirme içerebilir.|  
|REG_NOTIFY_CHANGE_SECURITY|Güvenlik tanımlayıcısı anahtarının değişiklikler arayan bildirin.|  
  
 `hEvent`  
 Bir olaya işleyin. Varsa *bAsync* parametredir TRUE, yöntem hemen döndürür ve değişiklikler, bu olay sinyal tarafından raporlanır. Varsa `bAsync` FALSE ' tır `hEvent` göz ardı edilir.  
  
 `bAsync`  
 Nasıl yöntemi değişiklikleri raporları belirten bir bayrak belirtir. Bu parametre TRUE ise, yöntem hemen döndürür ve belirtilen olay sinyal tarafından değişiklikleri raporlar. Bu parametre FALSE olduğunda, bir değişiklik meydana gelene kadar yöntemi döndürmüyor. Varsa `hEvent` geçerli bir olay belirtmiyor `bAsync` parametresi TRUE olamaz.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa, dönüş değeri ERROR_SUCCESS ' dir. Yöntem başarısız olursa, dönüş değeri WINERROR içinde tanımlanan bir sıfır olmayan hata kodudur. H.  
  
### <a name="remarks"></a>Açıklamalar  
  
> [!NOTE]
>  Belirtilen anahtarı sildiyseniz bu metodu çağıran uyarmaz.  
  
 Daha fazla ayrıntı ve örnek programı için bkz: [RegNotifyChangeKeyValue](http://msdn.microsoft.com/library/windows/desktop/ms724892).  
  
##  <a name="open"></a>CRegKey::Open  
 Belirtilen anahtarı'ni açıp ayarlamak için bu yöntemi çağırın [m_hKey](#m_hkey) bu anahtarın işlenecek.  
  
```
LONG Open(  
    HKEY hKeyParent,
    LPCTSTR lpszKeyName,
    REGSAM samDesired = KEY_READ | KEY_WRITE) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `hKeyParent`  
 Açık bir anahtarın tanımlayıcısı.  
  
 `lpszKeyName`  
 Açılan veya oluşturulacak bir anahtarın adını belirtir. Bu ad, bir alt olmalıdır `hKeyParent`.  
  
 `samDesired`  
 Anahtar güvenlik erişim. KEY_ALL_ACCESS varsayılan değerdir. Olası değerler ve açıklamaları listesi için bkz: [RegCreateKeyEx](http://msdn.microsoft.com/library/windows/desktop/ms724844) Windows SDK'sındaki.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, ERROR_SUCCESS döndürür; Aksi takdirde, sıfır olmayan bir hata değeri WINERROR içinde tanımlanır. H.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa `lpszKeyName` parametredir NULL veya noktaları boş bir dizesine **açık** yeni bir işleyici tarafından tanımlanan anahtarının açar `hKeyParent`, ancak herhangi bir önceden açılan tutamacı kapatmaz.  
  
 Farklı [CRegKey::Create](#create), **açık** henüz yoksa belirtilen anahtarı oluşturmaz.  
  
##  <a name="operator_hkey"></a>CRegKey::operator HKEY  
 Dönüştüren bir `CRegKey` bir HKEY nesnesine.  
  
```  
operator HKEY() const throw();
```  
  
##  <a name="operator_eq"></a>CRegKey::operator =  
 Atama işleci.  
  
```
CRegKey& operator= (CRegKey& key) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `key`  
 Kopyalamak için anahtar.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yeni anahtar için bir başvuru döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işleç ayırır `key` kendi geçerli nesneden ve atar `CRegKey` yerine nesne.  
  
##  <a name="querybinaryvalue"></a>CRegKey::QueryBinaryValue  
 Belirtilen değer adı için ikili verileri almak için bu yöntemi çağırın.  
  
```
LONG QueryBinaryValue(  
    LPCTSTR pszValueName,
    void* pValue,
    ULONG* pnBytes) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `pszValueName`  
 Sorgu değeri adını içeren bir null ile sonlandırılmış dize işaretçi.  
  
 `pValue`  
 Değer verisini alan arabellek işaretçi.  
  
 `pnBytes`  
 Tarafından arabelleğin bayt cinsinden boyutu belirten bir değişken işaretçi işaret için `pValue` parametresi. Yöntem döndüğünde, bu değişken arabelleğin kopyalanan verilerin boyutunu içerir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa, ERROR_SUCCESS döndürülür. Bir değer okumak yöntem başarısız olursa WINERROR içinde tanımlanan bir sıfır olmayan hata kodunu döndürür. H. Başvurulan veri türü REG_BINARY değilse ERROR_INVALID_DATA döndürülür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntemi kullanır **RegQueryValueEx** ve verileri doğru türde verdiğini onaylar. Bkz: [RegQueryValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724911) daha fazla ayrıntı için.  
  
> [!IMPORTANT]
>  Bu yöntem güvenilemez verileri okunurken, herhangi bir kayıt defteri konumu belirtmek arayan sağlar. Ayrıca, [RegQueryValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724911) bu yöntem tarafından kullanılan işlev sonlandırıldı NULL olan dizeleri açıkça işlemez. Her iki koşul için çağrıyı yapan kod tarafından denetlenmelidir.  
  
##  <a name="querydwordvalue"></a>CRegKey::QueryDWORDValue  
 Belirtilen değer adı DWORD verilerini almak için bu yöntemi çağırın.  
  
```
LONG QueryDWORDValue(  
    LPCTSTR pszValueName,
    DWORD& dwValue) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `pszValueName`  
 Sorgu değeri adını içeren bir null ile sonlandırılmış dize işaretçi.  
  
 `dwValue`  
 DWORD değerini alan bir arabellek işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa, ERROR_SUCCESS döndürülür. Bir değer okumak yöntem başarısız olursa WINERROR içinde tanımlanan bir sıfır olmayan hata kodunu döndürür. H. Başvurulan veri türü REG_DWORD değilse ERROR_INVALID_DATA döndürülür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntemi kullanır **RegQueryValueEx** ve verileri doğru türde verdiğini onaylar. Bkz: [RegQueryValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724911) daha fazla ayrıntı için.  
  
> [!IMPORTANT]
>  Bu yöntem güvenilemez verileri okunurken, herhangi bir kayıt defteri konumu belirtmek arayan sağlar. Ayrıca, [RegQueryValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724911) bu yöntem tarafından kullanılan işlev sonlandırıldı NULL olan dizeleri açıkça işlemez. Her iki koşul için çağrıyı yapan kod tarafından denetlenmelidir.  
  
##  <a name="queryguidvalue"></a>CRegKey::QueryGUIDValue  
 Belirtilen değer adı için GUID verileri almak için bu yöntemi çağırın.  
  
```
LONG QueryGUIDValue(  
    LPCTSTR pszValueName,
    GUID& guidValue) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `pszValueName`  
 Sorgu değeri adını içeren bir null ile sonlandırılmış dize işaretçi.  
  
 `guidValue`  
 İşaretçi bir değişkene GUID alır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa, ERROR_SUCCESS döndürülür. Bir değer okumak yöntem başarısız olursa WINERROR içinde tanımlanan bir sıfır olmayan hata kodunu döndürür. H. Başvurulan veri geçerli bir GUID değil ERROR_INVALID_DATA döndürülür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntemi kullanır `CRegKey::QueryStringValue` ve dize GUID kullanarak içine dönüştürür [CLSIDFromString](http://msdn.microsoft.com/library/windows/desktop/ms680589).  
  
> [!IMPORTANT]
>  Bu yöntem güvenilemez verileri okunurken, herhangi bir kayıt defteri konumu belirtmek arayan sağlar.  
  
##  <a name="querymultistringvalue"></a>CRegKey::QueryMultiStringValue  
 Belirtilen değer adı için çok dizeli verileri almak için bu yöntemi çağırın.  
  
```
LONG QueryMultiStringValue(  
    LPCTSTR pszValueName,
    LPTSTR pszValue,
    ULONG* pnChars) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `pszValueName`  
 Sorgu değeri adını içeren bir null ile sonlandırılmış dize işaretçi.  
  
 `pszValue`  
 Çok dizeli verileri alan bir arabellek işaretçi. Bir multistring iki null karakterleriyle sonlandırıldı null ile sonlandırılmış dizeler dizisidir.  
  
 `pnChars`  
 TCHARs gösterdiği arabellek boyutu `pszValue`. Yöntem döndüğünde `pnChars` boyutunda bir sonlandırma null karakter dahil olmak üzere alınan, multistring, TCHARs içerir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa, ERROR_SUCCESS döndürülür. Bir değer okumak yöntem başarısız olursa WINERROR içinde tanımlanan bir sıfır olmayan hata kodunu döndürür. H. Başvurulan veri türü REG_MULTI_SZ değilse ERROR_INVALID_DATA döndürülür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntemi kullanır **RegQueryValueEx** ve verileri doğru türde verdiğini onaylar. Bkz: [RegQueryValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724911) daha fazla ayrıntı için.  
  
> [!IMPORTANT]
>  Bu yöntem güvenilemez verileri okunurken, herhangi bir kayıt defteri konumu belirtmek arayan sağlar. Ayrıca, [RegQueryValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724911) bu yöntem tarafından kullanılan işlev sonlandırıldı NULL olan dizeleri açıkça işlemez. Her iki koşul için çağrıyı yapan kod tarafından denetlenmelidir.  
  
##  <a name="queryqwordvalue"></a>CRegKey::QueryQWORDValue  
 Belirtilen değer adı QWORD verilerini almak için bu yöntemi çağırın.  
  
```
LONG QueryQWORDValue(  
    LPCTSTR pszValueName,
    ULONGLONG& qwValue) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `pszValueName`  
 Sorgu değeri adını içeren bir null ile sonlandırılmış dize işaretçi.  
  
 `qwValue`  
 QWORD alan arabellek işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa, ERROR_SUCCESS döndürülür. Bir değer okumak yöntem başarısız olursa WINERROR içinde tanımlanan bir sıfır olmayan hata kodunu döndürür. H. Başvurulan veri türü REG_QWORD değilse ERROR_INVALID_DATA döndürülür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntemi kullanır **RegQueryValueEx** ve verileri doğru türde verdiğini onaylar. Bkz: [RegQueryValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724911) daha fazla ayrıntı için.  
  
> [!IMPORTANT]
>  Bu yöntem güvenilemez verileri okunurken, herhangi bir kayıt defteri konumu belirtmek arayan sağlar. Ayrıca, [RegQueryValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724911) bu yöntem tarafından kullanılan işlev sonlandırıldı NULL olan dizeleri açıkça işlemez. Her iki koşul için çağrıyı yapan kod tarafından denetlenmelidir.  
  
##  <a name="querystringvalue"></a>CRegKey::QueryStringValue  
 Belirtilen değer adı dize verilerini almak için bu yöntemi çağırın.  
  
```
LONG QueryStringValue(  
    LPCTSTR pszValueName,
    LPTSTR pszValue,
    ULONG* pnChars) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `pszValueName`  
 Sorgu değeri adını içeren bir null ile sonlandırılmış dize işaretçi.  
  
 `pszValue`  
 Dize verilerini alan arabellek işaretçi.  
  
 `pnChars`  
 TCHARs gösterdiği arabellek boyutu `pszValue`. Yöntem döndüğünde `pnChars` boyutunda bir sonlandırma null karakter dahil olmak üzere alınan, dize TCHARs içerir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa, ERROR_SUCCESS döndürülür. Bir değer okumak yöntem başarısız olursa WINERROR içinde tanımlanan bir sıfır olmayan hata kodunu döndürür. H. Başvurulan veri türü REG_SZ değilse ERROR_INVALID_DATA döndürülür. Yöntem ERROR_MORE_DATA, döndürüyorsa `pnChars` eşittir sıfır, gerekli arabellek boyutunu bayt cinsinden değil.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntemi kullanır **RegQueryValueEx** ve verileri doğru türde verdiğini onaylar. Bkz: [RegQueryValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724911) daha fazla ayrıntı için.  
  
> [!IMPORTANT]
>  Bu yöntem güvenilemez verileri okunurken, herhangi bir kayıt defteri konumu belirtmek arayan sağlar. Ayrıca, [RegQueryValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724911) bu yöntem tarafından kullanılan işlev sonlandırıldı NULL olan dizeleri açıkça işlemez. Her iki koşul için çağrıyı yapan kod tarafından denetlenmelidir.  
  
##  <a name="queryvalue"></a>CRegKey::QueryValue  
 Belirtilen değeri alanı için verileri almak için bu yöntemi çağırın [m_hKey](#m_hkey). Bu yöntem önceki sürümleri artık desteklenmemektedir ve olarak işaretlenmiş **ATL_DEPRECATED**.  
  
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
 `pszValueName`  
 Sorgu değeri adını içeren bir null ile sonlandırılmış dize işaretçi. Varsa `pszValueName` NULL veya boş bir dize "", yöntemi türünü alır ve verileri anahtarı için adlandırılmamış veya varsa varsayılan değer.  
  
 `pdwType`  
 İşaretçi bir değişkene belirtilen değerinde depolanan verilerin türünü gösteren bir kod alır. `pdwType` Parametre türü kodu gerekli değilse NULL olamaz.  
  
 `pData`  
 Değer verisini alan arabellek işaretçi. Veri gerekli değilse bu parametre NULL olabilir.  
  
 `pnBytes`  
 Tarafından arabelleğin bayt cinsinden boyutu belirten bir değişken işaretçi işaret için `pData` parametresi. Yöntem döndürüldüğünde, bu değişken kopyalanan verilerin boyutunu içerir *pData.*  
  
 `dwValue`  
 Değer alanın sayısal veriler.  
  
 `lpszValueName`  
 Sorgulanacak değer alanını belirtir.  
  
 `szValue`  
 Değer alanın dizesi verileri.  
  
 `pdwCount`  
 Dize veri boyutu. Değeri, başlangıçta boyutuna ayarlanır `szValue` arabellek.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, ERROR_SUCCESS döndürür; Aksi takdirde, sıfır olmayan hata kodu WINERROR içinde tanımlanır. H.  
  
### <a name="remarks"></a>Açıklamalar  
 İki özgün sürümü `QueryValue` artık desteklenmemektedir ve olarak işaretlenmiş **ATL_DEPRECATED**. Bu formlar kullandıysanız derleyici bir uyarı verecek.  
  
 RegQueryValueEx kalan yöntemini çağırır.  
  
> [!IMPORTANT]
>  Bu yöntem güvenilemez verileri okunurken, herhangi bir kayıt defteri konumu belirtmek arayan sağlar. Ayrıca, bu yöntem tarafından kullanılan RegQueryValueEx işlevi açıkça olan dizeleri işlemiyor `NULL` sonlandırıldı. Her iki koşul için çağrıyı yapan kod tarafından denetlenmelidir.  
  
##  <a name="recursedeletekey"></a>CRegKey::RecurseDeleteKey  
 Belirtilen anahtarı kayıt defterinden kaldırın ve tüm alt açıkça kaldırmak için bu yöntemi çağırın.  
  
```
LONG RecurseDeleteKey(LPCTSTR lpszKey) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 *lpszKey*  
 Silmek için anahtar adını belirtir. Bu ad, bir alt olmalıdır [m_hKey](#m_hkey).  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, ERROR_SUCCESS döndürür; Aksi takdirde, sıfır olmayan bir hata değeri WINERROR içinde tanımlanır. H.  
  
### <a name="remarks"></a>Açıklamalar  
 Anahtarı alt anahtarları varsa, anahtarı silmek için bu yöntemi çağırmanız gerekir.  
  
##  <a name="setbinaryvalue"></a>CRegKey::SetBinaryValue  
 Kayıt defteri anahtarının ikili değer ayarlamak için bu yöntemi çağırın.  
  
```
LONG SetBinaryValue(  
    LPCTSTR pszValueName,
    const void* pValue,
    ULONG nBytes) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `pszValueName`  
 Ayarlanacak değer adını içeren bir dize işaretçi. Bu ada sahip bir değer mevcut değilse, yöntem anahtarına ekler.  
  
 `pValue`  
 Belirtilen değer adıyla depolanması için verileri içeren bir arabellek işaretçi.  
  
 `nBytes`  
 Gösterdiği bilgilerinin bayt cinsinden boyutu belirtir `pValue` parametresi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa, dönüş değeri ERROR_SUCCESS ' dir. Yöntem başarısız olursa, dönüş değeri WINERROR içinde tanımlanan bir sıfır olmayan hata kodudur. H.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem [RegSetValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724923) değerini kayıt defterine yazılamıyor.  
  
##  <a name="setdwordvalue"></a>CRegKey::SetDWORDValue  
 Kayıt defteri anahtarı DWORD değerini ayarlamak için bu yöntemi çağırın.  
  
```
LONG SetDWORDValue(LPCTSTR pszValueName, DWORD dwValue) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `pszValueName`  
 Ayarlanacak değer adını içeren bir dize işaretçi. Bu ada sahip bir değer mevcut değilse, yöntem anahtarına ekler.  
  
 `dwValue`  
 Belirtilen değer adıyla depolanacak DWORD verileri.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa, dönüş değeri ERROR_SUCCESS ' dir. Yöntem başarısız olursa, dönüş değeri WINERROR içinde tanımlanan bir sıfır olmayan hata kodudur. H.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem [RegSetValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724923) değerini kayıt defterine yazılamıyor.  
  
##  <a name="setguidvalue"></a>CRegKey::SetGUIDValue  
 Kayıt defteri anahtarı GUID değerini ayarlamak için bu yöntemi çağırın.  
  
```
LONG SetGUIDValue(LPCTSTR pszValueName, REFGUID guidValue) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `pszValueName`  
 Ayarlanacak değer adını içeren bir dize işaretçi. Bu ada sahip bir değer mevcut değilse, yöntem anahtarına ekler.  
  
 `guidValue`  
 Belirtilen değer adıyla depolanması için GUID başvuru.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa, dönüş değeri ERROR_SUCCESS ' dir. Yöntem başarısız olursa, dönüş değeri WINERROR içinde tanımlanan bir sıfır olmayan hata kodudur. H.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntemi kullanır `CRegKey::SetStringValue` ve bir dize kullanarak GUID dönüştürür [StringFromGUID2](http://msdn.microsoft.com/library/windows/desktop/ms683893).  
  
##  <a name="setkeyvalue"></a>CRegKey::SetKeyValue  
 Belirtilen anahtar bir belirtilen değer alanına verileri depolamak için bu yöntemi çağırın.  
  
```
LONG SetKeyValue(  
    LPCTSTR lpszKeyName,
    LPCTSTR lpszValue,
    LPCTSTR lpszValueName = NULL) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszKeyName`  
 Açılan veya oluşturulacak anahtar adını belirtir. Bu ad, bir alt olmalıdır [m_hKey](#m_hkey).  
  
 `lpszValue`  
 Verilerin depolanması için belirtir. Bu parametre NULL olmayan olmalıdır.  
  
 `lpszValueName`  
 Ayarlanacak değer alanını belirtir. Bu ada sahip bir değer alan anahtarı zaten mevcut değilse eklenir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, ERROR_SUCCESS döndürür; Aksi takdirde, sıfır olmayan hata kodu WINERROR içinde tanımlanır. H.  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturmak veya açmak için bu yöntemi çağırabilmeniz `lpszKeyName` depolamak ve anahtar `lpszValue` verileri `lpszValueName` değeri alanı.  
  
##  <a name="setkeysecurity"></a>CRegKey::SetKeySecurity  
 Kayıt defteri anahtarının güvenlik ayarlamak için bu yöntemi çağırın.  
  
```
LONG SetKeySecurity(SECURITY_INFORMATION si, PSECURITY_DESCRIPTOR psd) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `si`  
 Ayarlamak için güvenlik tanımlayıcısı bileşenlerini belirtir. Değer bir birleşimi aşağıdaki değerlerden biri olabilir:  
  
|Değer|Açıklama|  
|-----------|-------------|  
|DACL_SECURITY_INFORMATION|Anahtarın isteğe bağlı erişim denetimi listesi (DACL) ayarlar. Arama işlemi nesnenin sahibi olmanız gerekir veya anahtar WRITE_DAC erişimi olmalıdır.|  
|GROUP_SECURITY_INFORMATION|Anahtarın birincil grup güvenlik tanımlayıcısı (SID) ayarlar. Arama işlemi nesnenin sahibi olmanız gerekir veya anahtar WRITE_OWNER erişimi olmalıdır.|  
|OWNER_SECURITY_INFORMATION|Anahtarın sahibi SID'si ayarlar. Anahtar WRITE_OWNER erişiminiz olmalıdır veya arama işlemi nesnenin sahibi olmanız veya etkin SE_TAKE_OWNERSHIP_NAME ayrıcalığına sahip olması gerekir.|  
|SACL_SECURITY_INFORMATION|Anahtarın sistem erişim denetimi listesi (SACL) ayarlar. Anahtar ACCESS_SYSTEM_SECURITY erişimi olması gerekir. Bu erişmek için uygun şekilde SE_SECURITY_NAME etkinleştirmektir [ayrıcalık](http://msdn.microsoft.com/library/windows/desktop/aa379306) arayanın geçerli erişim belirteci ACCESS_SYSTEM_SECURITY erişim için tanıtıcı açın ve ayrıcalık devre dışı bırakın.|  
  
 `psd`  
 İşaretçi bir [SECURITY_DESCRIPTOR](http://msdn.microsoft.com/library/windows/desktop/aa379561) yapısı için belirtilen anahtar ayarlamak için güvenlik özniteliklerini belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa, dönüş değeri ERROR_SUCCESS ' dir. Yöntem başarısız olursa, dönüş değeri WINERROR içinde tanımlanan bir sıfır olmayan hata kodudur. H.  
  
### <a name="remarks"></a>Açıklamalar  
 Anahtarın güvenlik özniteliklerini ayarlar. Bkz: [RegSetKeySecurity](http://msdn.microsoft.com/library/windows/desktop/aa379314) daha fazla ayrıntı için.  
  
##  <a name="setmultistringvalue"></a>CRegKey::SetMultiStringValue  
 Kayıt defteri anahtarının çok dizeli değer ayarlamak için bu yöntemi çağırın.  
  
```
LONG SetMultiStringValue(LPCTSTR pszValueName, LPCTSTR pszValue) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `pszValueName`  
 Ayarlanacak değer adını içeren bir dize işaretçi. Bu ada sahip bir değer mevcut değilse, yöntem anahtarına ekler.  
  
 `pszValue`  
 Belirtilen değer adıyla depolanması için çok dizeli veri işaretçi. Bir multistring iki null karakterleriyle sonlandırıldı null ile sonlandırılmış dizeler dizisidir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa, dönüş değeri ERROR_SUCCESS ' dir. Yöntem başarısız olursa, dönüş değeri WINERROR içinde tanımlanan bir sıfır olmayan hata kodudur. H.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem [RegSetValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724923) değerini kayıt defterine yazılamıyor.  
  
##  <a name="setqwordvalue"></a>CRegKey::SetQWORDValue  
 Kayıt defteri anahtarı QWORD değerini ayarlamak için bu yöntemi çağırın.  
  
```
LONG SetQWORDValue(LPCTSTR pszValueName, ULONGLONG qwValue) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `pszValueName`  
 Ayarlanacak değer adını içeren bir dize işaretçi. Bu ada sahip bir değer mevcut değilse, yöntem anahtarına ekler.  
  
 `qwValue`  
 Belirtilen değer adıyla depolanması için QWORD verileri.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa, dönüş değeri ERROR_SUCCESS ' dir. Yöntem başarısız olursa, dönüş değeri WINERROR içinde tanımlanan bir sıfır olmayan hata kodudur. H.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem [RegSetValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724923) değerini kayıt defterine yazılamıyor.  
  
##  <a name="setstringvalue"></a>CRegKey::SetStringValue  
 Kayıt defteri anahtarı dize değerini ayarlamak için bu yöntemi çağırın.  
  
```
LONG SetStringValue(  
    LPCTSTR pszValueName,
    LPCTSTR pszValue,
    DWORD dwType = REG_SZ) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `pszValueName`  
 Ayarlanacak değer adını içeren bir dize işaretçi. Bu ada sahip bir değer mevcut değilse, yöntem anahtarına ekler.  
  
 `pszValue`  
 Belirtilen değer adıyla depolanması için dize verilerini işaretçi.  
  
 `dwType`  
 Kayıt defterine yazılamıyor dize tür: REG_SZ (varsayılan) veya REG_EXPAND_SZ (için multistrings).  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa, dönüş değeri ERROR_SUCCESS ' dir. Yöntem başarısız olursa, dönüş değeri WINERROR içinde tanımlanan bir sıfır olmayan hata kodudur. H.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem [RegSetValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724923\(v=vs.85\).aspx) değerini kayıt defterine yazılamıyor.  
  
##  <a name="setvalue"></a>CRegKey::SetValue  
 Belirtilen değer alanında verileri depolamak için bu yöntemi çağırın [m_hKey](#m_hkey). Bu yöntem önceki sürümleri artık desteklenmemektedir ve olarak işaretlenmiş **ATL_DEPRECATED**.  
  
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
 `pszValueName`  
 Ayarlanacak değer adını içeren bir dize işaretçi. Bu ada sahip bir değer anahtar mevcut değilse, yöntem anahtarına ekler. Varsa `pszValueName` NULL veya boş bir dize "", yöntemi türünü ayarlar ve anahtarı için veri adlandırılmamış veya varsayılan değer.  
  
 `dwType`  
 Gösterdiği veri türünü gösteren bir kod belirtir `pValue` parametresi.  
  
 `pValue`  
 Belirtilen değer adıyla depolanması için verileri içeren bir arabellek işaretçi.  
  
 `nBytes`  
 Gösterdiği bilgilerinin bayt cinsinden boyutu belirtir `pValue` parametresi. Veri türü REG_SZ, REG_EXPAND_SZ veya REG_MULTI_SZ ise `nBytes` sonlandırma null karakteri boyutunu eklemeniz gerekir.  
  
 `hKeyParent`  
 Açık bir anahtarın tanımlayıcısı.  
  
 `lpszKeyName`  
 Açılan veya oluşturulacak bir anahtarın adını belirtir. Bu ad, bir alt olmalıdır `hKeyParent`.  
  
 `lpszValue`  
 Verilerin depolanması için belirtir. Bu parametre NULL olmayan olmalıdır.  
  
 `lpszValueName`  
 Ayarlanacak değer alanını belirtir. Bu ada sahip bir değer alan anahtarı zaten mevcut değilse eklenir.  
  
 `dwValue`  
 Verilerin depolanması için belirtir.  
  
 `bMulti`  
 False ise, dize türü REG_SZ gösterir. TRUE ise, dize türü REG_MULTI_SZ multistring gösterir.  
  
 `nValueLen`  
 Varsa `bMulti` doğrudur `nValueLen` uzunluğu *lpszValue* karakter dizesi. Varsa `bMulti` false, -1 değerini gösteriyorsa yöntemi uzunluğu otomatik olarak hesaplar.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, ERROR_SUCCESS döndürür; Aksi takdirde, sıfır olmayan hata kodu WINERROR içinde tanımlanır. H.  
  
### <a name="remarks"></a>Açıklamalar  
 İki özgün sürümü `SetValue` olarak işaretlenmiş **ATL_DEPRECATED** ve artık kullanılmalıdır. Bu formlar kullandıysanız derleyici bir uyarı verecek.  
  
 Üçüncü yöntem çağrılarını [RegSetValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724923).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [DCOM örnek](../../visual-cpp-samples.md)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
