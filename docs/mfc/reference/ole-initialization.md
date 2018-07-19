---
title: OLE başlatma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- afxdisp/AfxOleInit
- afxdisp/AfxEnableControlContainer
dev_langs:
- C++
helpviewer_keywords:
- OLE initialization
ms.assetid: aa8a54a7-24c3-4344-b2c6-dbcf6084fa31
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 330701c4fcc75d40e782d25baa55044b88852f50
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37337803"
---
# <a name="ole-initialization"></a>OLE Başlatma
Uygulamanın OLE sistem hizmetlerini kullanmadan önce OLE sistem DLL'lerini Başlat ve DLL'leri doğru sürüm olduğundan emin olun. `AfxOleInit` İşlevi OLE sistem DLL'lerini başlatır.  
  
### <a name="ole-initialization"></a>OLE Başlatma  
  
|||  
|-|-|  
|[Afxoleınit](#afxoleinit)|OLE kitaplıklarının başlatır.| 
|[AfxEnableControlContainer](#afxenablecontrolcontainer)|Uygulama nesnenizin içinde bu işlevi çağırın `InitInstance` kapsama OLE denetimlerinin desteğini etkinleştirmek için işlevi.| 


## <a name="afxenablecontrolcontainer"></a> AfxEnableControlContainer
Uygulama nesnenizin içinde bu işlevi çağırın `InitInstance` kapsama OLE denetimlerinin desteğini etkinleştirmek için işlevi.  
   
### <a name="syntax"></a>Sözdizimi    
```
void AfxEnableControlContainer( );  
```  
   
### <a name="remarks"></a>Açıklamalar  
 OLE denetimleri (artık ActiveX denetimleri olarak da bilinir) hakkında daha fazla bilgi için bkz: [ActiveX denetimi konuları](../mfc-activex-controls.md).  
   
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdisp.h  

  
##  <a name="afxoleinit"></a>  Afxoleınit  
 OLE desteği için uygulamayı başlatır.  
  
``` 
BOOL AFXAPI AfxOleInit(); 
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa sıfır dışı; 0 OLE sistem DLL'leri yanlış sürümlerinin yüklü olduğunu başlatma, büyük olasılıkla başarısız olur.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir MFC uygulaması OLE desteği başlatmak için bu işlevi çağırın. Bu işlev çağrıldığında aşağıdaki eylemler gerçekleşir:  
  
-   Çağıran uygulamanın geçerli Grup COM kitaplık başlatır. Daha fazla bilgi için [OleInitialize](http://msdn.microsoft.com/library/windows/desktop/ms690134).  
  
-   Bir ileti filtresi oluşturur, uygulama [ı](http://msdn.microsoft.com/library/windows/desktop/ms693740) arabirimi. Bu ileti filtresi çağrısı ile erişilebilir [AfxOleGetMessageFilter](application-control.md#afxolegetmessagefilter).  
  
> [!NOTE]
>  Varsa **Afxoleınit** çağrılır bir MFC DLL dosyasından çağrı başarısız olur. Bir DLL dosyasından çağrılırsa, OLE sistem daha önce çağıran uygulama tarafından başlatıldı, işlev varsayar hata oluşur.  
  
> [!NOTE]
>  MFC uygulamaları tek iş parçacıklı grup (STA) başlatılması gerekir. Eğer [CoInitializeEx](http://msdn.microsoft.com/library/windows/desktop/ms695279) içinde `InitInstance` geçersiz kılmak, COINIT_APARTMENTTHREADED (COINIT_MULTITHREADED yerine) belirtin. Daha fazla bilgi için bkz: MFC uygulaması olarak bir çok iş parçacıklı grup (828643) uygulamayı başlattığınızda yanıt vermeyi durduran [ http://support.microsoft.com/default.aspxscid=kb; en-us; 828643](http://support.microsoft.com/default.aspxscid=kb;en-us;828643).  

### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdisp.h

## <a name="see-also"></a>Ayrıca Bkz.  
 [Makroları ve genel öğeleri](../../mfc/reference/mfc-macros-and-globals.md)
