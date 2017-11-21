---
title: "CSettingsStoreSP sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSettingsStoreSP
- AFXSETTINGSSTORE/CSettingsStoreSP
- AFXSETTINGSSTORE/CSettingsStoreSP::CSettingsStoreSP
- AFXSETTINGSSTORE/CSettingsStoreSP::Create
- AFXSETTINGSSTORE/CSettingsStoreSP::SetRuntimeClass
dev_langs: C++
helpviewer_keywords:
- CSettingsStoreSP [MFC], CSettingsStoreSP
- CSettingsStoreSP [MFC], Create
- CSettingsStoreSP [MFC], SetRuntimeClass
ms.assetid: bcd37f40-cfd4-4d17-a5ce-3bfabe995dcc
caps.latest.revision: "18"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a30ca86898aa94a2c42f73b2f589c7fc7fc93634
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="csettingsstoresp-class"></a>CSettingsStoreSP sınıfı
`CSettingsStoreSP` Sınıftır örneklerini oluşturmak için kullanabileceğiniz bir yardımcı sınıfı [CSettingsStore sınıfı](../../mfc/reference/csettingsstore-class.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CSettingsStoreSP  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CSettingsStoreSP::CSettingsStoreSP](#csettingsstoresp)|Oluşturan bir `CSettingsStoreSP` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CSettingsStoreSP::Create](#create)|Türetilmiş bir sınıf örneği oluşturur `CSettingsStore`.|  
|[CSettingsStoreSP::SetRuntimeClass](#setruntimeclass)|Çalışma zamanı sınıf ayarlar. `Create` Yöntemi nesneleri oluşturmak için hangi sınıfının belirlemek üzere çalışma zamanı sınıfını kullanır.|  
  
### <a name="data-members"></a>Veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`m_dwUserData`|Depolanan özel kullanıcı verilerini `CSettingsStoreSP` nesnesi. Bu oluşturucusunun veriyi sağladığınız `CSettingsStoreSP` nesnesi.|  
|`m_pRegistry`|`CSettingsStore`-Türetilen nesnesinin `Create` yöntemi oluşturur.|  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanabileceğiniz `CSettingsStoreSP` bir XML dosyası veya veritabanı gibi başka konumlara tüm MFC kayıt defteri işlemlerini yönlendirmek için sınıf. Bunu yapmak için şu adımları izleyin:  
  
1.  Bir sınıf oluşturun (gibi `CMyStore`) ve bu sınıftan türetilen `CSettingsStore`.  
  
2.  Kullanım [DECLARE_DYNCREATE](run-time-object-model-services.md#declare_dyncreate) ve [IMPLEMENT_DYNCREATE](run-time-object-model-services.md#implement_dyncreate) özel makroları `CSettingsStore` dinamik oluşturulmasını sınıfı.  
  
3.  Sanal işlevleri geçersiz kılma ve uygulama `Read` ve `Write` özel sınıfınızda işlevleri. Okuma ve istenilen konuma veri yazmak için başka bir işlevsellik uygulayın.  
  
4.  Uygulamanızda arama `CSettingsStoreSP::SetRuntimeClass` ve bir işaretçi geçirin [CRuntimeClass yapısı](../../mfc/reference/cruntimeclass-structure.md) , sınıfından elde.  
  
 Framework genellikle kayıt defterine erişim olduğunda, bunu şimdi dinamik olarak özel sınıfının örneği ve okumak veya veri yazmak için kullanın.  
  
 `CSettingsStoreSP::SetRuntimeClass`Genel statik değişkeni kullanır. Bu nedenle, aynı anda yalnızca bir özel depo kullanılabilir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxsettingsstore.h  
  
##  <a name="create"></a>CSettingsStoreSP::Create  
 Türetilmiş bir nesne yeni bir örneğini oluşturur [CSettingsStore sınıfı](../../mfc/reference/csettingsstore-class.md).  
  
```  
CSettingsStore& CSettingsStoreSP Create(
    BOOL bAdmin,  
    BOOL bReadOnly);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`bAdmin`  
 Belirleyen bir Boolean parametresiyle olup bir `CSettingsStore` nesnesi, Yönetici modunda oluşturulur.  
  
 [in]`bReadOnly`  
 Belirleyen bir Boolean parametresiyle olup bir `CSettingsStore` nesnesi salt okunur erişim için oluşturulur.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yeni oluşturulan bir başvuru `CSettingsStore` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Yöntemini kullanabilirsiniz [CSettingsStoreSP::SetRuntimeClass](#setruntimeclass) ne nesnesi türü belirlemek için `CSettingsStoreSP::Create` oluşturur. Varsayılan olarak, bu yöntem oluşturur bir `CSettingsStore` nesnesi.  
  
 Oluşturursanız, bir `CSettingsStore` tüm kayıt defteri erişimi için varsayılan konumu: HKEY_LOCAL_MACHINE Yönetici modunda nesne. Aksi takdirde, varsayılan tüm kayıt defteri erişimi HKEY_CURRENT_USER konumudur.  
  
 Varsa `bAdmin` olan `TRUE`, uygulama yönetim haklarına sahip olmanız gerekir. Aksi takdirde, kayıt defteri erişmeye çalıştığında, işlem başarısız olur.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl kullanılacağı ortaya `Create` yöntemi `CSettingsStoreSP` sınıfı.  
  
 [!code-cpp[NVC_MFC_RibbonApp#33](../../mfc/reference/codesnippet/cpp/csettingsstoresp-class_1.cpp)]  
  
##  <a name="csettingsstoresp"></a>CSettingsStoreSP::CSettingsStoreSP  
 Oluşturan bir [CSettingsStoreSP sınıfı](../../mfc/reference/csettingsstoresp-class.md) nesnesi.  
  
```  
CSettingsStoreSP::CSettingsStoreSP(DWORD dwUserData = 0);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`dwUserData`  
 Kullanıcı tanımlı veri, `CSettingsStoreSP` nesne depolar.  
  
### <a name="remarks"></a>Açıklamalar  
 `CSettingsStoreSP` Nesne verilerini depolayan `dwUserData` korumalı üye değişkeninde `m_dwUserData`.  
  
##  <a name="setruntimeclass"></a>CSettingsStoreSP::SetRuntimeClass  
 Çalışma zamanı sınıf ayarlar. Yöntem [CSettingsStoreSP::Create](#create) çalışma zamanı sınıfı oluşturmak için nesne türünü belirlemek için kullanır.  
  
```  
static BOOL __stdcall CSettingsStoreSP::SetRuntimeClass(CRuntimeClass* pRTI);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pRTI`  
 Türetilmiş bir sınıf için çalışma zamanı sınıf bilgileri için bir işaretçi [CSettingsStore sınıfı](../../mfc/reference/csettingsstore-class.md).  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`başarılı olursa; `FALSE` sınıfı tarafından tanımladıysanız `pRTI` türetilmedi `CSettingsStore`.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanabileceğiniz [CSettingsStoreSP sınıfı](../../mfc/reference/csettingsstoresp-class.md) sınıflarından için `CSettingsStore`. Yöntem kullanmak `SetRuntimeClass` türetilmiş bir özel sınıfın nesnelerini oluşturmak isteyip istemediğinizi `CSettingsStore`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CSettingsStore sınıfı](../../mfc/reference/csettingsstore-class.md)
