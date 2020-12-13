---
description: 'Daha fazla bilgi edinin: görselleştirme Yöneticisi'
title: Seri Hale Getirme Yöneticisi
ms.date: 11/19/2018
helpviewer_keywords:
- Visualization Manager
ms.assetid: c9dd1365-27ac-42e5-8caa-1004525b4129
ms.openlocfilehash: b99331503e4e7e69cc5d8a19fde7641c1b1daeeb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97143214"
---
# <a name="visualization-manager"></a>Seri Hale Getirme Yöneticisi

Görsel yönetici, tüm uygulamanın görünümünü denetleyen bir nesnedir. Uygulamanıza yönelik tüm çizim kodunu koyabileceğiniz tek bir sınıf gibi davranır. MFC Kitaplığı çeşitli görsel Yöneticiler içerir. Ayrıca, uygulamanız için özel bir görünüm oluşturmak istiyorsanız kendi görsel yöneticinize da oluşturabilirsiniz. Aşağıdaki görüntüler farklı görsel Yöneticiler etkinleştirildiğinde aynı uygulamayı gösterir:

![CMFCVisualManagerWindows tarafından işlenen olarak MyApp](../mfc/media/vmwindows.png "CMFCVisualManagerWindows tarafından işlenen olarak MyApp") <br/>
CMFCVisualManagerWindows Visual Manager kullanan MyApp

![CMFCVisualManagerVS2005 tarafından işlenen olarak MyApp](../mfc/media/vmvs2005.png "CMFCVisualManagerVS2005 tarafından işlenen olarak MyApp") <br/>
CMFCVisualManagerVS2005 görsel Yöneticisi kullanan MyApp

![CMFCVisualManagerOfficeXP tarafından işlenen olarak MyApp](../mfc/media/vmofficexp.png "CMFCVisualManagerOfficeXP tarafından işlenen olarak MyApp") <br/>
CMFCVisualManagerOfficeXP görsel Yöneticisi kullanan MyApp

![CMFCVisualManagerOffice2003 tarafından işlenen olarak MyApp](../mfc/media/vmoffice2003.png "CMFCVisualManagerOffice2003 tarafından işlenen olarak MyApp") <br/>
CMFCVisualManagerOffice2003 görsel Yöneticisi kullanan MyApp

![CMFCVisualManagerOffice2007 tarafından işlenen olarak MyApp](../mfc/media/msoffice2007.png "CMFCVisualManagerOffice2007 tarafından işlenen olarak MyApp") <br/>
CMFCVisualManagerOffice2007 görsel Yöneticisi kullanan MyApp

Varsayılan olarak, görsel yönetici birkaç GUI öğesi için çizim kodunu tutar. Özel UI öğeleri sağlamak için, Visual Manager 'ın ilgili çizim yöntemlerini geçersiz kılmanız gerekir. Bu yöntemlerin listesi için bkz. [CMFCVisualManager sınıfı](../mfc/reference/cmfcvisualmanager-class.md). Özel bir görünüm sağlamak için geçersiz kılabileceğiniz Yöntemler, ile başlayan tüm yöntemlerdir `OnDraw` .

Uygulamanız yalnızca bir nesneye sahip olabilir `CMFCVisualManager` . Uygulamanız için görsel yöneticiye bir işaretçi almak için, [CMFCVisualManager:: GetInstance](../mfc/reference/cmfcvisualmanager-class.md#getinstance)statik işlevini çağırın. Tüm görsel Yöneticiler öğesinden devraldığı `CMFCVisualManager` `CMFCVisualManager::GetInstance` için, özel bir görsel yönetici oluştursanız bile, yöntem uygun görsel yöneticiye bir işaretçi alır.

Özel bir görsel yönetici oluşturmak istiyorsanız, zaten mevcut olan bir Visual Manager 'dan türetmeniz gerekir. ' Den türetmeye yönelik varsayılan sınıf `CMFCVisualManager` . Bununla birlikte, uygulamanız için istediğiniz kadar uygunsa, farklı bir görsel yönetici kullanabilirsiniz. Örneğin, `CMFCVisualManagerOffice2007` Visual Manager 'ı kullanmak isterseniz, ancak yalnızca ayırıcıların görünümünü değiştirmek istiyorsanız, özel sınıfınızı ' den türetebilirsiniz `CMFCVisualManagerOffice2007` . Bu senaryoda, yalnızca çizim ayırıcılarının üzerine yazmanız gerekir.

Uygulamanız için belirli bir görsel yöneticiyi kullanmanın iki yolu vardır. Tek yönlü [CMFCVisualManager:: SetDefaultManager](../mfc/reference/cmfcvisualmanager-class.md#setdefaultmanager) yöntemini çağırmak ve uygun görsel yöneticiyi parametre olarak iletmektir. Aşağıdaki kod örneği, `CMFCVisualManagerVS2005` Bu yöntemle Visual Manager 'ı nasıl kullanacağınızı gösterir:

```cpp
CMFCVisualManager::SetDefaultManager (RUNTIME_CLASS (CMFCVisualManagerVS2005));
```

Uygulamanızda bir Visual Manager kullanmanın diğer yolu el ile oluşturmaktır. Uygulama daha sonra işleme için bu yeni görsel yöneticiyi kullanacaktır. Ancak, uygulama başına yalnızca bir nesne olabileceğinden `CMFCVisualManager` , yenisini oluşturmadan önce geçerli Visual Manager 'ı silmeniz gerekir. Aşağıdaki örnekte, `CMyVisualManager` öğesinden türetilmiş özel bir görsel yöneticisidir `CMFCVisualManager` . Aşağıdaki yöntem, bir dizine bağlı olarak, uygulamanızı göstermek için hangi görsel yöneticinin kullanıldığını değiştirecek:

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
[CMFCVisualManager sınıfı](../mfc/reference/cmfcvisualmanager-class.md)
