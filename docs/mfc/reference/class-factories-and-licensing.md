---
title: Sınıf oluşturucular ve lisanslama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.macros.classes
dev_langs:
- C++
helpviewer_keywords:
- class factories [MFC], and licensing
ms.assetid: 53c4856a-4062-46db-9f69-dd4339f746b3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: abb9d5ca169edf28bb3f72c26e644894c12ccb93
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37336240"
---
# <a name="class-factories-and-licensing"></a>Sınıf Oluşturucular ve Lisanslama
OLE denetim örneği oluşturmak için bir kapsayıcı uygulaması denetimin sınıf üreteci üye işlevi çağırır. Gerçek bir OLE nesne denetiminizin olduğu için sınıf üreteci denetiminizin örnekleri oluşturmak için sorumludur. Her bir OLE denetim sınıfı, bir sınıf üreteci olması gerekir.  
  
 OLE denetimleri başka bir önemli özelliği, lisans zorlamak için kendi olanağıdır. ControlWizard, Denetim projeniz oluşturulurken lisans eklemenizi sağlar. Denetimini lisanslama ile ilgili daha fazla bilgi için bkz [ActiveX denetimleri: bir ActiveX denetimini lisanslama](../../mfc/mfc-activex-controls-licensing-an-activex-control.md).  
  
 Aşağıdaki tabloda çeşitli makrolar ve bildirmek ve denetim sınıf üreteci uygulamak için kullanılan işlevleri listeler ve denetiminizin lisans.  
  
### <a name="class-factories-and-licensing"></a>Sınıf Oluşturucular ve Lisanslama  
  
|||  
|-|-|  
|[DECLARE_OLECREATE_EX](#declare_olecreate_ex)|Sınıf üreteci için bir OLE denetim veya özellik sayfasına bildirir.|  
|[IMPLEMENT_OLECREATE_EX](#implement_olecreate_ex)|Denetimin uygulayan `GetClassID` işlevi ve bir sınıf üreteci örneğini bildirir.|  
|[BEGIN_OLEFACTORY](#begin_olefactory)|Herhangi bir lisans işlevlerin bildirimini başlar.|  
|[END_OLEFACTORY](#end_olefactory)|Herhangi bir lisans işlevlerin bildirimini sona erer.|  
|[AfxVerifyLicFile](#afxverifylicfile)|Bir denetimin belirli bir bilgisayar üzerinde kullanım için lisanslı olup olmadığını doğrular.|  
  
##  <a name="declare_olecreate_ex"></a>  DECLARE_OLECREATE_EX  
 Bir sınıf üreteci bildirir ve `GetClassID` denetim sınıfınızın bir üye işlevi.  
  
```   
DECLARE_OLECREATE_EX(class_name)   
```  
  
### <a name="parameters"></a>Parametreler  
 *$class_name*  
 Denetim sınıfı adı.  
  
### <a name="remarks"></a>Açıklamalar  
 Lisanslama desteklemeyen bir denetim için denetim sınıf üstbilgi dosyasında bu makroyu kullanın.  
  
 Not: Bu makroyu aşağıdaki kod örneği aynı amaca hizmet eder  
  
 [!code-cpp[NVC_MFCAxCtl#14](../../mfc/reference/codesnippet/cpp/class-factories-and-licensing_1.h)]  
  
### <a name="requirements"></a>Gereksinimler  
  **Üst bilgi** afxctl.h  
  
##  <a name="implement_olecreate_ex"></a>  IMPLEMENT_OLECREATE_EX  
 Denetimin sınıf üreteci uygular ve [GetClassID](../../mfc/reference/colecontrol-class.md#getclassid) denetim sınıfınızın bir üye işlevi.  
  
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
 *$class_name*  
 Denetim özellik sayfası sınıfının adı.  
  
 *external_name*  
 Uygulamalar için sunulan nesne adı.  
  
 *m, w1, w2, b1, b2, b3, b4, b5, b6, b7, b8*  
 Sınıfın CLSID bileşenleri. Bu parametreler hakkında daha fazla bilgi için açıklamalar için bkz. [ımplement_olecreate](run-time-object-model-services.md#implement_olecreate).  
  
### <a name="remarks"></a>Açıklamalar  
 Bu makro, DECLARE_OLECREATE_EX makrosu veya begın_olefactory ve END_OLEFACTORY makroları kullanan herhangi bir denetim sınıf için uygulama dosyasında yer almalıdır. Sunucunun dış adının, başka uygulamalar için sunulan OLE denetim tanımlayıcısıdır. Kapsayıcılar, bu denetim sınıfının bir nesnesi istemek için bu adı kullanın.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üst bilgi** afxctl.h  
  
##  <a name="begin_olefactory"></a>  BEGIN_OLEFACTORY  
 Denetim sınıfınızın üstbilgi dosyasında, sınıf üreteci bildirimi başlar.  
  
``` 
BEGIN_OLEFACTORY(class_name)  
```  
  
### <a name="parameters"></a>Parametreler  
 *$class_name*  
 Sınıf üreteci bu denetimi sınıfın adını belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Sınıf üreteci işlevleri lisanslama bildirimlerini hemen sonra begın_olefactory başlamalısınız.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üst bilgi** afxctl.h  
  
##  <a name="end_olefactory"></a>  END_OLEFACTORY  
 Denetimin sınıf üreteci bildirimi sona erer.  
  
```  
END_OLEFACTORY(class_name)   
```  
  
### <a name="parameters"></a>Parametreler  
 *$class_name*  
 Sınıf üreteci bu denetim sınıfı adı.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üst bilgi** afxctl.h  
  
##  <a name="afxverifylicfile"></a>  AfxVerifyLicFile  
 Lisans dosyası tarafından adlandırılan doğrulamak için bu işlevi çağırın `pszLicFileName` OLE denetimi için geçerlidir.  
  
```   
BOOL AFXAPI AfxVerifyLicFile(
    HINSTANCE  hInstance,  
    LPCTSTR  pszLicFileName,  
    LPOLESTR  pszLicFileContents,  
    UINT cch = -1); 
```  
  
### <a name="parameters"></a>Parametreler  
 *HINSTANCE*  
 Örnek tanıtıcısını lisanslı denetimle ilişkili dll.  
  
 *pszLicFileName*  
 Lisans dosya adını içeren bir null ile sonlandırılmış dizeye işaret eder.  
  
 *pszLicFileContents*  
 Lisans dosyanın başında bulunan dizisi eşleşmelidir bir bayt sırası işaret eder.  
  
 *cch*  
 Karakter sayısı *pszLicFileContents*.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Lisans dosyası var ve karakter dizisi ile başlayan olursa sıfır dışı *pszLicFileContents*; Aksi durumda 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa *cch* -1, bu işlev kullanır:  
  
 [!code-cpp[NVC_MFC_Utilities#36](../../mfc/codesnippet/cpp/class-factories-and-licensing_2.cpp)]  

### <a name="requirements"></a>Gereksinimler  
  **Üst bilgi** afxctl.h  

## <a name="see-also"></a>Ayrıca Bkz.  
 [Makroları ve genel öğeleri](../../mfc/reference/mfc-macros-and-globals.md)
