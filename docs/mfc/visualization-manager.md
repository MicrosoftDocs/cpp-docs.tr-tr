---
title: Seri Hale Getirme Yöneticisi
ms.date: 06/28/2018
helpviewer_keywords:
- Visualization Manager
ms.assetid: c9dd1365-27ac-42e5-8caa-1004525b4129
ms.openlocfilehash: befff860f50677f9c70c0fbb6b45ac528c36e773
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50521378"
---
# <a name="visualization-manager"></a>Seri Hale Getirme Yöneticisi

Görsel yöneticiyi tüm uygulama görünümünü denetleyen bir nesnedir. Bu, tek bir sınıf uygulamanız için çizim kodunu yere koyabilirsiniz işlevi görür. MFC kitaplığını birçok görsel Yöneticiler içerir. Uygulamanız için özel görünüm oluşturmak istiyorsanız, ayrıca kendi görsel yöneticiyi oluşturabilirsiniz. Farklı görsel Yöneticiler etkin olduğunda, aşağıdaki resimlerde aynı uygulama göster:

![CMFCVisualManagerWindows tarafından işlenen olarak MyApp](../mfc/media/vmwindows.png "vmwindows") CMFCVisualManagerWindows görsel yöneticiyi kullanan Uygulamam

![CMFCVisualManagerVS2005 tarafından işlenen olarak MyApp](../mfc/media/vmvs2005.png "vmvs2005") CMFCVisualManagerVS2005 görsel yöneticiyi kullanan Uygulamam

![CMFCVisualManagerOfficeXP tarafından işlenen olarak MyApp](../mfc/media/vmofficexp.png "vmofficexp") CMFCVisualManagerOfficeXP görsel yöneticiyi kullanan Uygulamam

![CMFCVisualManagerOffice2003 tarafından işlenen Uygulamam](../mfc/media/vmoffice2003.png "vmoffice2003") CMFCVisualManagerOffice2003 görsel yöneticiyi kullanan Uygulamam

![CMFCVisualManagerOffice2007 tarafından işlenen Uygulamam](../mfc/media/msoffice2007.png "msoffice2007") CMFCVisualManagerOffice2007 görsel yöneticiyi kullanan Uygulamam

Varsayılan olarak görsel yöneticiyi çeşitli GUI öğelerin çizim kodunu korur. Özel kullanıcı Arabirimi öğeleri sağlamak için görsel yöneticiyi ilgili çizim yöntemleri geçersiz kılmanız gerekir. Bu yöntemlerin listesi için bkz: [CMFCVisualManager sınıfı](../mfc/reference/cmfcvisualmanager-class.md). Özel bir görünümünü sağlamak için geçersiz kılabilirsiniz yöntemleri ile başlayan tüm yöntemlerin olması `OnDraw`.

Yalnızca bir uygulamanız olabilir `CMFCVisualManager` nesne. Görsel yöneticiyi uygulamanız için bir işaretçi alma için statik işlev çağrısı [CMFCVisualManager::GetInstance](../mfc/reference/cmfcvisualmanager-class.md#getinstance). Tüm görsel Yöneticiler devralınacak çünkü `CMFCVisualManager`, `CMFCVisualManager::GetInstance` yöntemi alacak bir işaretçi uygun görsel yöneticiyi için bile özel bir görsel yöneticiyi oluşturun.

Özel bir görsel yöneticiyi oluşturmak istiyorsanız, zaten bir görsel yöneticiyi türetilmesi gerekir. Varsayılan sınıf türetmek için `CMFCVisualManager`. Ancak, uygulamanız için istediğinize daha iyi benzer, farklı bir görsel yöneticiyi kullanabilirsiniz. Örneğin kullanmayı istiyorlardı, `CMFCVisualManagerOffice2007` , özel bir sınıftan türetilen, ancak görsel yöneticiyi istiyordu yalnızca ayırıcılar nasıl göründüğünü değiştirmek `CMFCVisualManagerOffice2007`. Bu senaryoda yalnızca ayırıcılar çizmek için yöntemleri üzerine yazmalıdır.

Uygulamanız için belirli bir görsel yöneticiyi kullanmak için olası iki yolu vardır. Çağrılacak yollarından biri olduğunu [CMFCVisualManager::SetDefaultManager](../mfc/reference/cmfcvisualmanager-class.md#setdefaultmanager) yöntemi ve pass uygun görsel yöneticiyi bir parametre olarak. Aşağıdaki kod örneği, nasıl kullanacağınız gösterilir `CMFCVisualManagerVS2005` bu yöntemle görsel yöneticiyi:

```cpp
CMFCVisualManager::SetDefaultManager (RUNTIME_CLASS (CMFCVisualManagerVS2005));
```

Bir görsel yöneticiyi kullanmak için başka bir şekilde el ile oluşturmanız sağlamaktır. Uygulama, daha sonra bu yeni görsel yöneticiyi işleme için kullanır. Ancak, çünkü tek olabilir `CMFCVisualManager` nesne uygulama başına yeni bir tane oluşturmadan önce geçerli görsel yöneticiyi silmeye olacaktır. Aşağıdaki örnekte, `CMyVisualManager` türetilen özel bir görsel Yöneticisi `CMFCVisualManager`. Aşağıdaki yöntem, hangi görsel yöneticiyi dizin bağlı olarak uygulamanızı görüntülemek için kullanılan değişir:

```cpp
void CMyApp::SetSkin (int index)
{
    if (CMFCVisualManager::GetInstance() != NULL)
    {
        delete CMFCVisualManager::GetInstance();
    }

    switch (index)
    {
    case DEFAULT_STYLE:
        // The following statement creates a new CMFCVisualManager
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

## <a name="see-also"></a>Ayrıca bkz.

[Kullanıcı arabirimi öğeleri](../mfc/user-interface-elements-mfc.md)<br/>
[CMFCVisualManager Sınıfı](../mfc/reference/cmfcvisualmanager-class.md)
