---
title: CSettingsStoreSP sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CSettingsStoreSP
- AFXSETTINGSSTORE/CSettingsStoreSP
- AFXSETTINGSSTORE/CSettingsStoreSP::CSettingsStoreSP
- AFXSETTINGSSTORE/CSettingsStoreSP::Create
- AFXSETTINGSSTORE/CSettingsStoreSP::SetRuntimeClass
dev_langs:
- C++
helpviewer_keywords:
- CSettingsStoreSP [MFC], CSettingsStoreSP
- CSettingsStoreSP [MFC], Create
- CSettingsStoreSP [MFC], SetRuntimeClass
ms.assetid: bcd37f40-cfd4-4d17-a5ce-3bfabe995dcc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1cf84e2e7db6f829cb7afcd1831521b4f94535bd
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/05/2018
ms.locfileid: "37850793"
---
# <a name="csettingsstoresp-class"></a>CSettingsStoreSP sınıfı
`CSettingsStoreSP` Örneklerini oluşturmak için kullanabileceğiniz bir yardımcı sınıfı [CSettingsStore sınıfı](../../mfc/reference/csettingsstore-class.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CSettingsStoreSP  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CSettingsStoreSP::CSettingsStoreSP](#csettingsstoresp)|Oluşturur bir `CSettingsStoreSP` nesne.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CSettingsStoreSP::Create](#create)|Türetilen bir sınıfın örneğini oluşturur `CSettingsStore`.|  
|[CSettingsStoreSP::SetRuntimeClass](#setruntimeclass)|Çalışma zamanı sınıf ayarlar. `Create` Yöntemi, hangi sınıfı oluşturmak için nesne belirlemek üzere çalışma zamanı sınıfı kullanır.|  
  
### <a name="data-members"></a>Veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`m_dwUserData`|Depolanan özel kullanıcı verilerini `CSettingsStoreSP` nesne. Bu verileri oluşturucusunun içinde sağladığınız `CSettingsStoreSP` nesne.|  
|`m_pRegistry`|`CSettingsStore`-Türetilmiş nesnesinin `Create` yöntemi oluşturur.|  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanabileceğiniz `CSettingsStoreSP` tüm MFC kayıt defteri işlemlerini bir XML dosyasına veya veritabanı gibi diğer konumlara yönlendirmek için sınıf. Bunu yapmak için şu adımları izleyin:  
  
1.  Bir sınıf oluşturun (gibi `CMyStore`) ve türetmeniz `CSettingsStore`.  
  
2.  Kullanım [DECLARE_DYNCREATE](run-time-object-model-services.md#declare_dyncreate) ve [IMPLEMENT_DYNCREATE](run-time-object-model-services.md#implement_dyncreate) özel makrolarla `CSettingsStore` dinamik oluşturmayı etkinleştirmek için sınıf.  
  
3.  Sanal işlevleri geçersiz kılma ve uygulama `Read` ve `Write` özel sınıfınıza işlevleri. Okumak ve istenen konumunuza veri yazmak için başka bir işlevlerini uygular.  
  
4.  Uygulamanızda, çağrı `CSettingsStoreSP::SetRuntimeClass` ve işaretçi geçirin [CRuntimeClass yapısı](../../mfc/reference/cruntimeclass-structure.md) sizin sınıfınızdan elde.  
  
 Framework, genellikle kayıt defterine erişim zaman, şimdi dinamik olarak, özel bir sınıf örneği ve verileri okuma veya yazma için kullanın.  
  
 `CSettingsStoreSP::SetRuntimeClass` Genel statik değişken kullanır. Bu nedenle, bir kerede yalnızca bir özel depo kullanılabilir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxsettingsstore.h  
  
##  <a name="create"></a>  CSettingsStoreSP::Create  
 Türetilen bir nesne yeni bir örneğini oluşturur [CSettingsStore sınıfı](../../mfc/reference/csettingsstore-class.md).  
  
```  
CSettingsStore& CSettingsStoreSP Create(
    BOOL bAdmin,  
    BOOL bReadOnly);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bYönetim*  
 Belirleyen bir Boole parametresi olup olmadığını bir `CSettingsStore` nesnesi, Yönetici modunda oluşturulur.  
  
 [in] *bReadOnly*  
 Belirleyen bir Boole parametresi olup olmadığını bir `CSettingsStore` nesnesi salt okunur erişim için oluşturulur.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yeni oluşturulan bir başvuru `CSettingsStore` nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Yöntemi kullanabileceğiniz [CSettingsStoreSP::SetRuntimeClass](#setruntimeclass) ne nesnesi türü belirlemek için `CSettingsStoreSP::Create` oluşturacaksınız. Varsayılan olarak, bu yöntem oluşturur bir `CSettingsStore` nesne.  
  
 Oluşturursanız, bir `CSettingsStore` tüm kayıt defteri erişimi için varsayılan konum şudur HKEY_LOCAL_MACHINE Yönetici modunda nesne. Aksi takdirde, varsayılan tüm kayıt defteri erişimini HKEY_CURRENT_USER konumudur.  
  
 Varsa *bYönetim* doğru ise, uygulama, yönetim haklarına sahip olmanız gerekir. Aksi takdirde, kayıt defteri erişmeye çalıştığında bu başarısız olur.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnek nasıl kullanılacağını gösterir `Create` yöntemi `CSettingsStoreSP` sınıfı.  
  
 [!code-cpp[NVC_MFC_RibbonApp#33](../../mfc/reference/codesnippet/cpp/csettingsstoresp-class_1.cpp)]  
  
##  <a name="csettingsstoresp"></a>  CSettingsStoreSP::CSettingsStoreSP  
 Oluşturur bir [CSettingsStoreSP sınıfı](../../mfc/reference/csettingsstoresp-class.md) nesne.  
  
```  
CSettingsStoreSP::CSettingsStoreSP(DWORD dwUserData = 0);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *dwUserData*  
 Kullanıcı tanımlı veri, `CSettingsStoreSP` nesnesini depolar.  
  
### <a name="remarks"></a>Açıklamalar  
 `CSettingsStoreSP` Nesne verilerden depolar *dwUserData* korumalı üye değişkeni içinde `m_dwUserData`.  
  
##  <a name="setruntimeclass"></a>  CSettingsStoreSP::SetRuntimeClass  
 Çalışma zamanı sınıf ayarlar. Yöntem [CSettingsStoreSP::Create](#create) çalışma zamanı sınıfı oluşturmak için nesne türüne belirlemek için kullanır.  
  
```  
static BOOL __stdcall CSettingsStoreSP::SetRuntimeClass(CRuntimeClass* pRTI);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pRTI*  
 Türetilen bir sınıf için çalışma zamanı sınıf bilgileri işaretçisi [CSettingsStore sınıfı](../../mfc/reference/csettingsstore-class.md).  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa TRUE; YANLIŞ bir sınıf tarafından tanımlanan *pRTI* türünden türetilmediğinden `CSettingsStore`.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanabileceğiniz [CSettingsStoreSP sınıfı](../../mfc/reference/csettingsstoresp-class.md) sınıflardan türetme `CSettingsStore`. Bu yöntemi kullanmak `SetRuntimeClass` türetilen özel bir sınıfın nesnelerini oluşturmak istiyorsanız `CSettingsStore`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CSettingsStore Sınıfı](../../mfc/reference/csettingsstore-class.md)
