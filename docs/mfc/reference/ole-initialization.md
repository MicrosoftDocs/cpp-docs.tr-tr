---
title: "OLE başlatma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- afxdisp/AfxOleInit
- afxdisp/AfxEnableControlContainer
dev_langs: C++
helpviewer_keywords: OLE initialization
ms.assetid: aa8a54a7-24c3-4344-b2c6-dbcf6084fa31
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 014d0679be8a03b60c2e759b36c056b35784be78
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="ole-initialization"></a>OLE Başlatma
Bir uygulama OLE Sistem Hizmetleri kullanabilmeniz için OLE sistem DLL'leri başlatma ve DLL'ler sürümünün doğru olduğundan emin olun gerekir. **Afxoleınit** işlevi OLE sistem DLL'leri başlatır.  
  
### <a name="ole-initialization"></a>OLE Başlatma  
  
|||  
|-|-|  
|[Afxoleınit](#afxoleinit)|OLE kitaplıklarının başlatır.| 
|[AfxEnableControlContainer](#afxenablecontrolcontainer)|Bu işlev, uygulama nesnesinin çağrı `InitInstance` OLE denetimlerinin kapsama desteğini etkinleştirmek için işlevi.| 


## <a name="afxenablecontrolcontainer"></a>AfxEnableControlContainer
Bu işlev, uygulama nesnesinin çağrı `InitInstance` OLE denetimlerinin kapsama desteğini etkinleştirmek için işlevi.  
   
### <a name="syntax"></a>Sözdizimi    
```
void AfxEnableControlContainer( );  
```  
   
### <a name="remarks"></a>Açıklamalar  
 OLE denetimleri (ActiveX denetimlerini şimdi denir) hakkında daha fazla bilgi için bkz: [ActiveX denetimi konuları](../mfc-activex-controls.md).  
   
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdisp.h  

  
##  <a name="afxoleinit"></a>Afxoleınit  
 OLE desteği için uygulamayı başlatır.  
  
``` 
BOOL AFXAPI AfxOleInit(); 
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; OLE sistem DLL'leri yanlış sürümlerinin yüklü olduğundan başlatma, büyük olasılıkla başarısız olursa 0.  
  
### <a name="remarks"></a>Açıklamalar  
 OLE desteği için MFC uygulaması başlatmak için bu işlevini çağırın. Bu işlev çağrıldığında, aşağıdaki eylemler gerçekleşir:  
  
-   Çağıran uygulamanın geçerli Grup COM kitaplıkta başlatır. Daha fazla bilgi için bkz: [OleInitialize](http://msdn.microsoft.com/library/windows/desktop/ms690134).  
  
-   Bir ileti filtresi oluşturur, uygulama [ı](http://msdn.microsoft.com/library/windows/desktop/ms693740) arabirimi. Bu ileti filtresi çağrısıyla erişilebilir [AfxOleGetMessageFilter](application-control.md#afxolegetmessagefilter).  
  
> [!NOTE]
>  Varsa **Afxoleınit** adı verilen bir MFC DLL dosyasından çağrı başarısız olur. DLL'den çağrılırsa, OLE sistem önceden çağıran uygulama tarafından başlatıldı, işlevi varsayar çünkü hata oluşur.  
  
> [!NOTE]
>  MFC uygulamaları tek iş parçacıklı (STA) başlatılması gerekir. Çağırırsanız [CoInitializeEx](http://msdn.microsoft.com/library/windows/desktop/ms695279) içinde `InitInstance` geçersiz kılma, belirtin `COINIT_APARTMENTTHREADED` (yerine `COINIT_MULTITHREADED`). Daha fazla bilgi için bkz: MFC uygulaması olarak bir birden çok iş parçacıklı grup (828643) uygulama başlattığınızda yanıt vermiyor [http://support.microsoft.com/default.aspxscid=kb;en-us;828643](http://support.microsoft.com/default.aspxscid=kb;en-us;828643).  

### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdisp.h

## <a name="see-also"></a>Ayrıca Bkz.  
 [Makroları ve genel öğeleri](../../mfc/reference/mfc-macros-and-globals.md)
