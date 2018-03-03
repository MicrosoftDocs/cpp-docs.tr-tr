---
title: "Seri hale getirme Yöneticisi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- Visualization Manager
ms.assetid: c9dd1365-27ac-42e5-8caa-1004525b4129
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 654ffc0f3fb4c33f153f3389442486ffa86b74a8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="visualization-manager"></a>Seri Hale Getirme Yöneticisi
Görsel Yöneticisi tüm uygulama görünümünü denetleyen bir nesnedir. Tek bir sınıf olarak burada, uygulamanız için tüm çizim kodu koyabilirsiniz yapar. MFC kitaplığını birkaç visual yöneticileri içerir. Uygulamanız için özel görünüm oluşturmak istiyorsanız visual yöneticiniz de oluşturabilirsiniz. Farklı görsel yöneticileri etkinleştirildiğinde aşağıdaki görüntüleri aynı uygulama göster:  
  
 ![CMFCVisualManagerWindows tarafından işlenen olarak Uygulamam](../mfc/media/vmwindows.png "vmwindows")  
CMFCVisualManagerWindows visual Yöneticisi'ni kullanan Uygulamam  
  
 ![CMFCVisualManagerVS2005 tarafından işlenen olarak Uygulamam](../mfc/media/vmvs2005.png "vmvs2005")  
CMFCVisualManagerVS2005 visual Yöneticisi'ni kullanan Uygulamam  
  
 ![CMFCVisualManagerOfficeXP tarafından işlenen olarak Uygulamam](../mfc/media/vmofficexp.png "vmofficexp")  
CMFCVisualManagerOfficeXP visual Yöneticisi'ni kullanan Uygulamam  
  
 ![CMFCVisualManagerOffice2003 tarafından işlenen Uygulamam](../mfc/media/vmoffice2003.png "vmoffice2003")  
CMFCVisualManagerOffice2003 visual Yöneticisi'ni kullanan Uygulamam  
  
 ![CMFCVisualManagerOffice2007 tarafından işlenen Uygulamam](../mfc/media/msoffice2007.png "msoffice2007")  
CMFCVisualManagerOffice2007 visual Yöneticisi'ni kullanan Uygulamam  
  
 Varsayılan olarak, visual Yöneticisi birkaç GUI öğesi çizim kodunu bulundurur. Özel kullanıcı Arabirimi öğeleri sağlamak için visual Yöneticisi'nin ilgili çizim yöntemleri geçersiz kılmanız gerekir. Bu yöntemlerin listesi için bkz: [CMFCVisualManager sınıfı](../mfc/reference/cmfcvisualmanager-class.md). Özel bir görünümünü sağlamak için geçersiz kılabilirsiniz yöntemleri ile başlayan tüm yöntemler şunlardır `OnDraw`.  
  
 Uygulamanızı yalnızca bir bulunabilir `CMFCVisualManager` nesnesi. Visual Yöneticisi, uygulamanız için bir işaretçi elde etmek için statik işlev çağrısı [CMFCVisualManager::GetInstance](../mfc/reference/cmfcvisualmanager-class.md#getinstance). Tüm visual yöneticileri öğesinden devraldığı `CMFCVisualManager`, `CMFCVisualManager::GetInstance` yöntemi alırsınız bir işaretçi uygun visual Yöneticisi için özel bir görsel Yöneticisi oluşturmak olsa bile.  
  
 Özel bir görsel Yöneticisi oluşturmak istiyorsanız, zaten varolan bir visual Yöneticisi'nden türetilmesi gerekir. Öğesinden türetilen için varsayılan sınıf `CMFCVisualManager`. Ancak, daha iyi uygulamanız için istediğiniz benzer ise farklı bir görsel Yöneticisi kullanabilirsiniz. Örneğin, kullanmak isterse `CMFCVisualManagerOffice2007` visual Yöneticisi, ancak istediği yalnızca ayırıcılar nasıl göründüğünü değiştirmek, özel sınıfından türetilen `CMFCVisualManagerOffice2007`. Bu senaryoda, yalnızca ayırıcılar çizim yöntemleri üzerine yazmanız gerekir.  
  
 Uygulamanız için bir özel görsel Yöneticisi'ni kullanmak için iki olası yolu vardır. Tek yönlü çağırmaktır [CMFCVisualManager::SetDefaultManager](../mfc/reference/cmfcvisualmanager-class.md#setdefaultmanager) yöntemi ve uygun visual Yöneticisi bir parametre olarak geçirin. Aşağıdaki kod örneğinde nasıl kullanacağınız gösterilmiştir `CMFCVisualManagerVS2005` visual Yöneticisi bu yöntem ile:  
  
```  
CMFCVisualManager::SetDefaultManager (RUNTIME_CLASS (CMFCVisualManagerVS2005));
```  
  
 Uygulamanızda bir görsel Yöneticisi'ni kullanmak için diğer el ile oluşturmak için yoludur. Uygulama için tüm işlemeyi sonra bu yeni visual Yöneticisi'ni kullanır. Ancak, olabilir çünkü tek `CMFCVisualManager` nesne uygulama başına yenisini oluşturmadan önce geçerli visual Yöneticisi silmek olacaktır. Aşağıdaki örnekte, `CMyVisualManager` türetilen özel bir görsel Yöneticisi `CMFCVisualManager`. Aşağıdaki yöntem, visual Yöneticisi'ne bağlı olarak bir dizin uygulamanızı görüntülemek için kullanılan değişir:  
  
```  
void CMyApp::SetSkin (int index)  
{  
    if (CMFCVisualManager::GetInstance() != NULL)  
 {  
    delete CMFCVisualManager::GetInstance();

 }  
 
    switch (index)  
 {  
    case DEFAULT_STYLE: *// The following statement creates a new CMFCVisualManager  
    CMFCVisualManager::GetInstance();
break;  
 
    case CUSTOM_STYLE:  
    new CMyVisualManager;  
    break; 
 
    default: 
    CMFCVisualManager::GetInstance();
break;  
 }  
 
    CMFCVisualManager::GetInstance()->RedrawAll();

} 
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kullanıcı arabirimi öğeleri](../mfc/user-interface-elements-mfc.md)   
 [CMFCVisualManager Sınıfı](../mfc/reference/cmfcvisualmanager-class.md)
