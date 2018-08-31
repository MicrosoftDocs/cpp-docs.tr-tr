---
title: CSettingsStore sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1731c32506ec0e9c4c392ff9429e28e5b71b3c7c
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43221138"
---
# <a name="csettingsstore-class"></a>CSettingsStore sınıfı
Windows API işlevlerini, kayıt defterine erişmek için kullandığınız bir nesne yönelimli bir arabirim sağlayan sarmalar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CSettingsStore : public CObject  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CSettingsStore::CSettingsStore](#csettingsstore)|Oluşturur bir `CSettingsStore` nesne.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CSettingsStore::Close](#close)|Kayıt defteri anahtarı kapatır.|  
|[CSettingsStore::CreateKey](#createkey)|Belirtilen anahtarı açar veya henüz yoksa oluşturur.|  
|[CSettingsStore::DeleteKey](#deletekey)|Belirtilen anahtarı ve tüm alt öğelerini siler.|  
|[CSettingsStore::DeleteValue](#deletevalue)|Açık anahtar için belirtilen değer siler.|  
|[CSettingsStore::Open](#open)|Belirtilen anahtarı'nı açar.|  
|[CSettingsStore::Read](#read)|Belirtilen bir anahtar değeri için verileri alır.|  
|[CSettingsStore::Write](#write)|Açık anahtarı altındaki kayıt defteri değeri yazar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Üye işlevleri `CreateKey` ve `Open` çok benzer. Kayıt defteri anahtarı zaten varsa `CreateKey` ve `Open` aynı şekilde işlev. Ancak, kayıt defteri anahtarı mevcut değilse `CreateKey` ise oluşturacağı `Open` bir hata değeri döndürür.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte, Aç ve okuma yöntemleri kullanmak gösterilmektedir `CSettingsStore` sınıfı. Bu kod parçacığı parçasıdır [araç ipucu gösterim örneği](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_ToolTipDemo#1](../../mfc/reference/codesnippet/cpp/csettingsstore-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CSettingsStore`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxsettingsstore.h  
  
##  <a name="close"></a>  CSettingsStore::Close  
 Kayıt defteri anahtarı kapatır.  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, bu yöntem yıkıcıdan çağrılır [CSettingsStore sınıfı](../../mfc/reference/csettingsstore-class.md).  
  
##  <a name="createkey"></a>  CSettingsStore::CreateKey  
 Bir kayıt defteri anahtarı açar veya henüz yoksa oluşturur.  
  
```  
virtual BOOL CreateKey(LPCTSTR pszPath);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pszPath*  
 Oluşturulacak veya açılan bir anahtarın adını belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 başarılıysa 0; Aksi halde sıfır olmayan bir değer.  
  
### <a name="remarks"></a>Açıklamalar  
 `CreateKey` kullanan `m_hKey` kökü olarak kayıt defteri sorgular. Arar *pszPath* alt olarak `m_hKey`. Anahtar mevcut değilse `CreateKey` oluşturur. Aksi halde, anahtar açılır. `CreateKey` Daha sonra Ayarlar `m_hKey` açık veya oluşturulan anahtarı.  
  
##  <a name="csettingsstore"></a>  CSettingsStore::CSettingsStore  
 Oluşturur bir `CSettngsStore` nesne.  
  
```  
CSettingsStore(
    BOOL bAdmin,  
    BOOL bReadOnly);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bYönetim*  
 Belirten bir Boole parametresi olmadığını `CSettingsStore` nesne Yönetici modunda çalışan.  
  
 [in] *bReadOnly*  
 Belirten bir Boole parametresi olmadığını `CSettingsStore` nesnesi salt okunur erişim modunda oluşturulur.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa *bYönetim* TRUE olarak ayarlandığında `m_hKey` üye değişkeni ayarlanır **HKEY_LOCAL_MACHINE**. Ayarlarsanız *bYönetim* false olarak `m_hKey` ayarlanır **HKEY_CURRENT_USER**.  
  
 Güvenlik erişimi bağımlı *bReadOnly* parametresi. Varsa *bReadonly* yanlış, güvenlik erişimi ayarlanacak **KEY_ALL_ACCESS**. Varsa *bReadyOnly* TRUE ise bir birleşimi için güvenlik erişimi ayarlayacak **KEY_QUERY_VALUE, KEY_NOTIFY** ve **KEY_ENUMERATE_SUB_KEYS**. Kayıt defteri ile birlikte güvenlik erişim hakkında daha fazla bilgi için bkz. [kayıt defteri anahtarı güvenlik ve erişim hakları](/windows/desktop/SysInfo/registry-key-security-and-access-rights).  
  
 Yok Edicisi `CSettingsStore` sürümleri `m_hKey` otomatik olarak.  
  
##  <a name="deletekey"></a>  CSettingsStore::DeleteKey  
 Kayıt defterinden bir anahtar ve tüm alt öğelerini siler.  
  
```  
virtual BOOL DeleteKey(
    LPCTSTR pszPath,  
    BOOL bAdmin = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pszPath*  
 Silinecek anahtar adı.  
  
 [in] *bYönetim*  
 Anahtarı silmek için anahtar konumunu belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa sıfır dışı; Aksi durumda 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem başarısız olur `CSettingsStore` salt okunur modda bir nesnedir.  
  
 Parametre *bYönetim* sıfır `DeleteKey` anahtarı silmek altında arar **HKEY_CURRENT_USER**. Varsa *bYönetim* sıfır değilse, `DeleteKey` anahtarı silmek altında arar **HKEY_LOCAL_MACHINE**.  
  
##  <a name="deletevalue"></a>  CSettingsStore::DeleteValue  
 Bir değer siler `m_hKey`.  
  
```  
virtual BOOL DeleteValue(LPCTSTR pszValue);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pszValue*  
 Kaldırmak için değer alanını belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa sıfır dışı; Aksi durumda 0.  
  
##  <a name="open"></a>  CSettingsStore::Open  
 Bir kayıt defteri anahtarı'nı açar.  
  
```  
virtual BOOL Open(LPCTSTR pszPath);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pszPath*  
 Bir kayıt defteri anahtarı adı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa sıfır dışı; Aksi durumda 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, belirtilen anahtar başarıyla açıldıktan sonra bu ayarlar `m_hKey` bu anahtarın işlenecek.  
  
##  <a name="read"></a>  CSettingsStore::Read  
 Bir kayıt defteri anahtarından değer okur.  
  
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
 [in] *pszKey*  
 Kayıt defterinden okumak için değerin adını içeren null ile sonlandırılmış bir dize işaretçisi.  
  
 [out] *iVal*  
 Kayıt defteri anahtarından okuma değerini alan bir tamsayı değişkenine başvuru.  
  
 [out] *dwVal*  
 Kayıt defteri anahtarından okuma değerini alan bir 32-bit çift sözcük değişkenine başvuru.  
  
 [out] *sVal*  
 Kayıt defteri anahtarından okuma değerini alan bir dize değişkeni başvuru.  
  
 [out] *scStringList*  
 Kayıt defteri anahtarından okuma değerini alan bir dize listesi değişkenine başvuru.  
  
 [out] *scArray*  
 Kayıt defteri anahtarından okuma değerini alan bir dize dizi değişkenine başvuru.  
  
 [out] *dwcArray*  
 Kayıt defteri anahtarından okuma değerini alan bir 32-bit çift sözcük dizi değişkenine başvuru.  
  
 [out] *wcArray*  
 Kayıt defteri anahtarından okuma değerini alan bir 16 bit sözcük dizi değişkenine başvuru.  
  
 [out] *bcArray*  
 Kayıt defteri anahtarından okuma değerini alan bir bayt dizisi değişkenine başvuru.  
  
 [out] *Lppoınt*  
 Başvuru için bir işaretçi bir `POINT` kayıt defteri anahtarından değer alan yapısı okuyun.  
  
 [out] *dikdörtgen*  
 Başvuru bir [CRect](../../atl-mfc-shared/reference/crect-class.md) değeri alan değişken kayıt defteri anahtarından okuma.  
  
 [out] *ppData*  
 İşaretçi değeri alan veri işaretçisi, kayıt defteri anahtarından okuma.  
  
 [out] *pBytes*  
 Bir işaretsiz tamsayı değişkeni işaretçisi. Bu değişken arabellek boyutunu alır, *ppData* işaret eder.  
  
 [out] *listesi*  
 Başvuru bir [CObList](../../mfc/reference/coblist-class.md) değeri alan değişken kayıt defteri anahtarından okuma.  
  
 [out] *obj*  
 Başvuru bir [CObject](../../mfc/reference/cobject-class.md) değeri alan değişken kayıt defteri anahtarından okuma.  
  
 [out] *pObj*  
 Başvuru için bir işaretçi bir `CObject` değeri alan değişken kayıt defteri anahtarından okuma.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa sıfır dışı; Aksi durumda 0.  
  
### <a name="remarks"></a>Açıklamalar  
 `Read` denetler *pszKey* alt olarak `m_hKey`.  
  
##  <a name="write"></a>  CSettingsStore::Write  
 Açık anahtarı altındaki kayıt defteri değeri yazar.  
  
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
 [in] *pszKey*  
 Ayarlanacak değerin adını içeren bir dize işaretçisi.  
  
 [in] *iVal*  
 Depolamak için verileri içeren bir tamsayı değişkenine başvuru.  
  
 [in] *dwVal*  
 Verileri depolamak için bir 32-bit çift sözcük değişkenine başvuru.  
  
 [in] *pszVal*  
 Verileri depolamak için bir null ile sonlandırılmış dize değişkeni işaretçisi.  
  
 [in] *scStringList*  
 Başvuru bir [CStringList](../../mfc/reference/cstringlist-class.md) depolamak için verileri içeren bir değişkeni.  
  
 [in] *bcArray*  
 Depolamak için verileri içeren bir bayt dizisi değişken başvuru.  
  
 [in] *scArray*  
 Depolamak için verileri içeren bir dize dizi değişkeni başvuru.  
  
 [in] *dwcArray*  
 Verileri depolamak için bir 32-bit çift sözcük dizi değişkeni başvuru.  
  
 [in] *wcArray*  
 Depolamak için verileri içeren bir 16 bit sözcük dizi değişkenine başvuru.  
  
 [in] *dikdörtgen*  
 Başvuru bir [CRect](../../atl-mfc-shared/reference/crect-class.md) depolamak için verileri içeren bir değişkeni.  
  
 [in] *Lppoınt*  
 Başvuru için bir işaretçi bir `POINT` depolamak için verileri içeren bir değişkeni.  
  
 [in] *pData*  
 Verileri depolamak için içeren arabellek için işaretçi.  
  
 [in] *nBytes*  
 Hangi verilerin bayt cinsinden boyutunu belirtir *pData* parametresi noktaları.  
  
 [in] *listesi*  
 Başvuru bir [CObList](../../mfc/reference/coblist-class.md) depolamak için verileri içeren bir değişkeni.  
  
 [in] *obj*  
 Başvuru bir [CObject](../../mfc/reference/cobject-class.md) depolamak için verileri içeren bir değişkeni.  
  
 [in] *pObj*  
 Bir işaretçi işaretçisi bir `CObject` depolamak için verileri içeren bir değişkeni.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa TRUE; Aksi durumda FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Kayıt defterine yazmak için ayarlamanız gerekir *bReadOnly* oluşturduğunuzda sıfır olmayan bir değer için bir [CSettingsStore](../../mfc/reference/csettingsstore-class.md) nesne. Daha fazla bilgi için [CSettingsStore::CSettingsStore](#csettingsstore).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CWinAppEx Sınıfı](../../mfc/reference/cwinappex-class.md)
