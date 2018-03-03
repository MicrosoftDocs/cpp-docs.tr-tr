---
title: "Sınıf oluşturucular ve lisanslama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros.classes
dev_langs:
- C++
helpviewer_keywords:
- class factories [MFC], and licensing
ms.assetid: 53c4856a-4062-46db-9f69-dd4339f746b3
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 79710cb1fa67ec8315fe287364126f88b4b498d7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="class-factories-and-licensing"></a>Sınıf Oluşturucular ve Lisanslama
OLE denetim örneği oluşturmak için bir kapsayıcı uygulama denetimin sınıf Factory üye işlevi çağırır. Denetim gerçek bir OLE nesne olduğundan, denetiminizi örneklerini oluşturmak için üreteci sorumludur. Her OLE denetim sınıfı bir üreteci olması gerekir.  
  
 Başka bir önemli OLE denetimleri lisans zorlamak için kendi yeteneği özelliğidir. ControlWizard, Denetim projenizi oluşturma sırasında lisans eklemenizi sağlar. Makaleyi denetimini lisanslama ile ilgili daha fazla bilgi için bkz: [ActiveX denetimleri: bir ActiveX denetimini lisanslama](../../mfc/mfc-activex-controls-licensing-an-activex-control.md).  
  
 Aşağıdaki tabloda çeşitli makrolar ve İşlevler bildirme ve denetiminizin üreteci uygulamak için kullanılan listeler ve denetiminizin lisans.  
  
### <a name="class-factories-and-licensing"></a>Sınıf Oluşturucular ve Lisanslama  
  
|||  
|-|-|  
|[DECLARE_OLECREATE_EX](#declare_olecreate_ex)|OLE denetim veya özellik sayfası sınıfı Fabrika bildirir.|  
|[IMPLEMENT_OLECREATE_EX](#implement_olecreate_ex)|Denetimin uygulayan `GetClassID` işlev ve üreteci örneği bildirir.|  
|[BEGIN_OLEFACTORY](#begin_olefactory)|Hiçbir lisans işlevlerin bildirimini başlar.|  
|[END_OLEFACTORY](#end_olefactory)|Hiçbir lisans işlevlerin bildirimini sona erer.|  
|[AfxVerifyLicFile](#afxverifylicfile)|Bir denetim belirli bir bilgisayardaki kullanmak için lisanslı olup olmadığını doğrular.|  
  
##  <a name="declare_olecreate_ex"></a>DECLARE_OLECREATE_EX  
 Bir sınıf fabrikası bildirir ve `GetClassID` denetim sınıfınızın üye işlevi.  
  
```   
DECLARE_OLECREATE_EX(class_name)   
```  
  
### <a name="parameters"></a>Parametreler  
 *class_name*  
 Denetim sınıfı adı.  
  
### <a name="remarks"></a>Açıklamalar  
 Lisans desteklemeyen denetimi için denetim sınıfı üstbilgi dosyasında bu makrosu kullanın.  
  
 Not: Bu makrosu aşağıdaki kod örneği aynı amaca hizmet eder  
  
 [!code-cpp[NVC_MFCAxCtl#14](../../mfc/reference/codesnippet/cpp/class-factories-and-licensing_1.h)]  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxctl.h  
  
##  <a name="implement_olecreate_ex"></a>IMPLEMENT_OLECREATE_EX  
 Denetimin sınıf üreticisi uygular ve [GetClassID](../../mfc/reference/colecontrol-class.md#getclassid) denetim sınıfınızın üye işlevi.  
  
```   
IMPLEMENT_OLECREATE_EX(
   class_name,   
    external_name,    
    l,   
    w1,   
    w2,   
    b1,   
    b2,   
    b3,   
    b4,   
    b5,   
    b6,   
    b7,
    b8)   
```  
  
### <a name="parameters"></a>Parametreler  
 *class_name*  
 Denetim özellik sayfası sınıfı adı.  
  
 *external_name*  
 Uygulamalar için kullanıma sunulan nesne adı.  
  
 *l, w1, w2, b1, b2, b3, b4, b5, b6, b7, b8*  
 Sınıfının bileşenlerinin **CLSID**. Bu parametreler hakkında daha fazla bilgi için açıklamalar için bkz: [ımplement_olecreate](run-time-object-model-services.md#implement_olecreate).  
  
### <a name="remarks"></a>Açıklamalar  
 Bu makrosu kullanan herhangi bir denetim sınıf uygulama dosyada görünmelidir `DECLARE_OLECREATE_EX` makrosu veya `BEGIN_OLEFACTORY` ve `END_OLEFACTORY` makroları. Dış başka uygulamalar için kullanıma sunulan OLE denetimi tanıtıcısı adıdır. Kapsayıcılar, bu denetim sınıfın bir nesnesi istemek için bu adı kullanın.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxctl.h  
  
##  <a name="begin_olefactory"></a>BEGIN_OLEFACTORY  
 Sınıf Fabrikanızda denetim sınıfınızın üstbilgi dosyası bildirimi başlar.  
  
``` 
BEGIN_OLEFACTORY(class_name)  
```  
  
### <a name="parameters"></a>Parametreler  
 *class_name*  
 Sınıf üreticisi bu denetim sınıfın adını belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 İşlevler lisans üreteci bildirimlerini hemen sonra başlamalıdır `BEGIN_OLEFACTORY`.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxctl.h  
  
##  <a name="end_olefactory"></a>END_OLEFACTORY  
 Denetimin sınıf üreticisi bildirimi sona erer.  
  
```  
END_OLEFACTORY(class_name)   
```  
  
### <a name="parameters"></a>Parametreler  
 *class_name*  
 Bu sınıf üreticisi control sınıfı adı.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxctl.h  
  
##  <a name="afxverifylicfile"></a>AfxVerifyLicFile  
 Lisans dosyası tarafından adlı doğrulamak için bu işlevi çağırmak `pszLicFileName` OLE denetimi için geçerlidir.  
  
```   
BOOL AFXAPI AfxVerifyLicFile(
    HINSTANCE  hInstance,  
    LPCTSTR  pszLicFileName,  
    LPOLESTR  pszLicFileContents,  
    UINT cch = -1); 
```  
  
### <a name="parameters"></a>Parametreler  
 `hInstance`  
 Lisanslı denetimi ile ilişkilendirilmiş DLL örneği tanıtıcısı.  
  
 `pszLicFileName`  
 Lisans filename içeren bir null olarak sonlandırılan bir karakter dizesi noktalarına.  
  
 `pszLicFileContents`  
 Lisans dosyasının başında bulunan sırası eşleşmelidir bir bayt dizisine noktaları.  
  
 `cch`  
 Karakter sayısını `pszLicFileContents`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Lisans dosyası varsa ve karakter dizisi ile başlayan sıfır olmayan `pszLicFileContents`; Aksi halde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa `cch` -1 ' dir bu işlev kullanır:  
  
 [!code-cpp[NVC_MFC_Utilities#36](../../mfc/codesnippet/cpp/class-factories-and-licensing_2.cpp)]  

### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxctl.h  

## <a name="see-also"></a>Ayrıca Bkz.  
 [Makroları ve genel öğeleri](../../mfc/reference/mfc-macros-and-globals.md)
