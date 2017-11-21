---
title: "CSettingsStore sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
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
dev_langs: C++
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
caps.latest.revision: "29"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d30a06cc420b5e9f00f0340e92295ca629ad6fee
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="csettingsstore-class"></a>CSettingsStore sınıfı
Windows API işlevleri, kayıt defterine erişmek için kullandığınız bir nesne yönelimli bir arabirim sağlayan sarmalar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CSettingsStore : public CObject  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CSettingsStore::CSettingsStore](#csettingsstore)|Oluşturan bir `CSettingsStore` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CSettingsStore::Close](#close)|Kayıt defteri anahtarı kapatır.|  
|[CSettingsStore::CreateKey](#createkey)|Belirtilen anahtarı açar veya henüz yoksa oluşturur.|  
|[CSettingsStore::DeleteKey](#deletekey)|Belirtilen anahtarı ve tüm alt öğelerini siler.|  
|[CSettingsStore::DeleteValue](#deletevalue)|Belirtilen değer açık anahtarın siler.|  
|[CSettingsStore::Open](#open)|Belirtilen anahtarı açar.|  
|[CSettingsStore::Read](#read)|Belirtilen bir anahtar değeri için verileri alır.|  
|[CSettingsStore::Write](#write)|Kayıt defteri anahtarı açılamıyor altında bir değer yazar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Üye işlevleri `CreateKey` ve `Open` çok benzer. Kayıt defteri anahtarı zaten varsa, `CreateKey` ve `Open` aynı şekilde işlev. Bununla birlikte, kayıt defteri anahtarı mevcut değilse `CreateKey` ancak oluşturacağı `Open` bir hata değeri döndürür.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek açık ve okuma yöntemlerinin kullanımı gösterilmiştir `CSettingsStore` sınıfı. Bu kod parçacığını parçası olan [araç ipucu gösterim örneği](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_ToolTipDemo#1](../../mfc/reference/codesnippet/cpp/csettingsstore-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CSettingsStore`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxsettingsstore.h  
  
##  <a name="close"></a>CSettingsStore::Close  
 Kayıt defteri anahtarı kapatır.  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, bu yöntem yıkıcısı çağrılır [CSettingsStore sınıfı](../../mfc/reference/csettingsstore-class.md).  
  
##  <a name="createkey"></a>CSettingsStore::CreateKey  
 Bir kayıt defteri anahtarı açar veya henüz yoksa oluşturur.  
  
```  
virtual BOOL CreateKey(LPCTSTR pszPath);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pszPath`  
 Açılan veya oluşturulacak bir anahtarın adını belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 başarılı olursa 0; Aksi takdirde sıfır olmayan bir değer.  
  
### <a name="remarks"></a>Açıklamalar  
 `CreateKey`kullanan `m_hKey` kayıt defteri sorguları kökü olarak. Arar `pszPath` bir alt olarak `m_hKey`. Anahtar mevcut değilse `CreateKey` oluşturur. Aksi halde, anahtar açar. `CreateKey`Ardından, ayarlar `m_hKey` açılan veya oluşturulan anahtarı.  
  
##  <a name="csettingsstore"></a>CSettingsStore::CSettingsStore  
 Oluşturur bir `CSettngsStore` nesnesi.  
  
```  
CSettingsStore(
    BOOL bAdmin,  
    BOOL bReadOnly);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`bAdmin`  
 Belirten Boolean parametre olup olmadığını `CSettingsStore` nesne Yönetici modunda çalışan.  
  
 [in]`bReadOnly`  
 Belirten Boolean parametre olup olmadığını `CSettingsStore` nesnesi salt okunur modda oluşturulur.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa `bAdmin` ayarlanır `false`, `m_hKey` üye değişkeni ayarlanmış `HKEY_LOCAL_MACHINE`. Ayarlarsanız `bAdmin` için `true`, `m_hKey` ayarlanır `HKEY_CURRENT_USER`.  
  
 Güvenlik erişimi bağlıdır `bReadOnly` parametresi. Varsa `bReadonly` olan `false`, güvenlik erişimi ayarlanacak `KEY_ALL_ACCESS`. Varsa `bReadyOnly` olan `true`, güvenlik erişimi için bir birleşimini ayarlanacak `KEY_QUERY_VALUE, KEY_NOTIFY` ve `KEY_ENUMERATE_SUB_KEYS`. Kayıt defteri ile birlikte güvenlik erişim hakkında daha fazla bilgi için bkz: [kayıt defteri anahtarı güvenliği ve erişim hakları](http://msdn.microsoft.com/library/windows/desktop/ms724878).  
  
 Yıkıcı için `CSettingsStore` serbest `m_hKey` otomatik olarak.  
  
##  <a name="deletekey"></a>CSettingsStore::DeleteKey  
 Bir anahtarı ve tüm alt öğelerini kayıt defterinden siler.  
  
```  
virtual BOOL DeleteKey(
    LPCTSTR pszPath,  
    BOOL bAdmin = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pszPath`  
 Silinecek anahtarın adı.  
  
 [in]`bAdmin`  
 Silmek için anahtar konumunu belirten anahtar.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem başarısız olur `CSettingsStore` nesnesidir salt okunur modda.  
  
 Varsa parametresi `bAdmin` sıfır `DeleteKey` altında silmek anahtar arar `HKEY_CURRENT_USER`. Varsa `bAdmin` sıfır olmayan, olan `DeleteKey` altında silmek anahtar arar `HKEY_LOCAL_MACHINE`.  
  
##  <a name="deletevalue"></a>CSettingsStore::DeleteValue  
 Arasında bir değer siler `m_hKey`.  
  
```  
virtual BOOL DeleteValue(LPCTSTR pszValue);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pszValue`  
 Kaldırmak için değer alanını belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
##  <a name="open"></a>CSettingsStore::Open  
 Bir kayıt defteri anahtarı açar.  
  
```  
virtual BOOL Open(LPCTSTR pszPath);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pszPath`  
 Bir kayıt defteri anahtarı adı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem belirtilen anahtarı başarıyla açıldıktan sonra Ayarlar `m_hKey` bu anahtarın işlenecek.  
  
##  <a name="read"></a>CSettingsStore::Read  
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
 [in]`pszKey`  
 Kayıt defterinden okunacak değerinin adını içeren null ile sonlandırılmış bir dize işaretçi.  
  
 [out]`iVal`  
 Kayıt defteri anahtarından okumak değerini alan bir tamsayı değişken başvuru.  
  
 [out]`dwVal`  
 Kayıt defteri anahtarından okumak değerini alan bir 32-bit çift word değişken başvuru.  
  
 [out]`sVal`  
 Kayıt defteri anahtarından okumak değerini alan bir dize değişkeni referansı.  
  
 [out]`scStringList`  
 Kayıt defteri anahtarından okumak değerini alan bir dize listesi değişkeni referansı.  
  
 [out]`scArray`  
 Kayıt defteri anahtarından okumak değerini alan bir dize dizisi değişkeni referansı.  
  
 [out]`dwcArray`  
 Kayıt defteri anahtarından okumak değerini alan bir 32-bit çift word dizi değişkeni referansı.  
  
 [out]`wcArray`  
 Kayıt defteri anahtarından okumak değerini alan bir 16 bit word dizi değişkeni referansı.  
  
 [out]`bcArray`  
 Kayıt defteri anahtarından okumak değerini alan bir bayt dizi değişkeni referansı.  
  
 [out]`lpPoint`  
 Bir işaretçi başvuru bir `POINT` değerini alan yapısı kayıt defteri anahtarından okumak.  
  
 [out]`rect`  
 Başvuru bir [CRect](../../atl-mfc-shared/reference/crect-class.md) değerini alan değişken kayıt defteri anahtarından okumak.  
  
 [out]`ppData`  
 Kayıt defteri anahtarından değer aldığı veri için bir işaretçi işaretçi okuyun.  
  
 [out]`pBytes`  
 İşaretçi bir işaretsiz tamsayı değişken. Bu değişken arabellek boyutunu alır, `ppData` işaret eder.  
  
 [out]`list`  
 Başvuru bir [CObList](../../mfc/reference/coblist-class.md) değerini alan değişken kayıt defteri anahtarından okumak.  
  
 [out]`obj`  
 Başvuru bir [CObject](../../mfc/reference/cobject-class.md) değerini alan değişken kayıt defteri anahtarından okumak.  
  
 [out]`pObj`  
 Bir işaretçi başvuru bir `CObject` değerini alan değişken kayıt defteri anahtarından okumak.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 `Read`denetler `pszKey` bir alt olarak `m_hKey`.  
  
##  <a name="write"></a>CSettingsStore::Write  
 Kayıt defteri anahtarı açılamıyor altında bir değer yazar.  
  
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
 [in]`pszKey`  
 Ayarlanacak değer adını içeren bir dize işaretçi.  
  
 [in]`iVal`  
 Depolamak için gerekli verileri içeren bir tamsayı değişken başvuru.  
  
 [in]`dwVal`  
 Veri içeren bir 32-bit çift word değişkeni referansı.  
  
 [in]`pszVal`  
 İşaretçi depolamak için gerekli verileri içeren bir dize null ile sonlandırılmış değişkenine.  
  
 [in]`scStringList`  
 Başvuru bir [CStringList](../../mfc/reference/cstringlist-class.md) depolamak için gerekli verileri içeren değişken.  
  
 [in]`bcArray`  
 Veri içeren bir bayt dizisi değişkeni referansı.  
  
 [in]`scArray`  
 Veri içeren bir dize dizisi değişkeni referansı.  
  
 [in]`dwcArray`  
 Veri içeren bir 32-bit çift word dizi değişkeni referansı.  
  
 [in]`wcArray`  
 Veri içeren bir 16 bit word dizi değişkeni referansı.  
  
 [in]`rect`  
 Başvuru bir [CRect](../../atl-mfc-shared/reference/crect-class.md) depolamak için gerekli verileri içeren değişken.  
  
 [in]`lpPoint`  
 Bir işaretçi başvuru bir `POINT` depolamak için gerekli verileri içeren değişken.  
  
 [in]`pData`  
 İşaretçi depolamak için gerekli verileri içeren bir arabellek.  
  
 [in]`nBytes`  
 Hangi verilerin bayt cinsinden boyutu belirtir `pData` parametresi noktaları.  
  
 [in]`list`  
 Başvuru bir [CObList](../../mfc/reference/coblist-class.md) depolamak için gerekli verileri içeren değişken.  
  
 [in]`obj`  
 Başvuru bir [CObject](../../mfc/reference/cobject-class.md) depolamak için gerekli verileri içeren değişken.  
  
 [in]`pObj`  
 Bir işaretçi işaretçi bir `CObject` depolamak için gerekli verileri içeren değişken.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`başarılı olursa; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Kayıt defterine yazma için ayarlamanız gerekir `bReadOnly` oluşturduğunuzda sıfır olmayan bir değer için bir [CSettingsStore](../../mfc/reference/csettingsstore-class.md) nesnesi. Daha fazla bilgi için bkz: [CSettingsStore::CSettingsStore](#csettingsstore).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CWinAppEx sınıfı](../../mfc/reference/cwinappex-class.md)
