---
title: Yeni belgeler, pencereler ve görünümler oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MDI [MFC], creating windows
- window objects [MFC], creating
- objects [MFC], creating document objects
- MFC default objects
- frame windows [MFC], creating
- windows [MFC], MDI
- MFC, documents
- view objects [MFC], creating
- windows [MFC], creating
- overriding, default view behavior
- views [MFC], initializing
- customizing MFC default objects
- MFC, frame windows
- MFC, views
- MDI [MFC], frame windows
- child windows [MFC], creating MDI
- view objects [MFC]
- document objects [MFC], creating
- MFC default objects [MFC], customizing
- views [MFC], overriding default behavior
- initializing views [MFC]
ms.assetid: 88aa1f5f-2078-4603-b16b-a2b4c7b4a2a3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 89d929f4d7419e027a1018c4b0b33a4e42416613
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="creating-new-documents-windows-and-views"></a>Yeni Belgeler, Pencereler ve Görünümler Oluşturma
Aşağıdaki şekil, belgeler, görünümler ve çerçeve pencereleri oluşturma işlemine genel bakış verin. Katılımcı nesnelerde odaklanmak diğer makaleler ek ayrıntılar sağlanmaktadır.  
  
 Tamamlandıktan sonra bu işlemi, birlikte çalışan nesneleri var ve birbirlerine işaretçileri saklayın. Aşağıdaki şekil nesneleri oluşturulduğu dizisi gösterir. Şekil başka bir şekil dizisi izleyebilirsiniz.  
  
 ![Bir belge oluşturmak için dizisi](../mfc/media/vc387l1.gif "vc387l1")  
Bir belge oluşturma sırası  
  
 ![Çerçeve pencere oluşturma dizisi](../mfc/media/vc387l2.png "vc387l2")  
Bir çerçeve pencere oluşturma dizisi  
  
 ![Bir görünüm oluşturmak için dizisi](../mfc/media/vc387l3.gif "vc387l3")  
Bir görünüm oluşturma sırası  
  
 Sınıfları nasıl yeni bir belge, Görünüm ve çerçeve pencere nesneleri framework başlatır hakkında daha fazla bilgi için bkz [CDocument](../mfc/reference/cdocument-class.md), [CView](../mfc/reference/cview-class.md), [CFrameWnd](../mfc/reference/cframewnd-class.md), [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md), ve [Cmdıchildwnd](../mfc/reference/cmdichildwnd-class.md) MFC Kitaplığı Başvurusu. Ayrıca bkz. [Teknik Not 22](../mfc/tn022-standard-commands-implementation.md), açıklayan oluşturma ve başlatma işlemleri daha fazla kendi tartışma için standart komutların framework'ün altında `New` ve **açık** üzerinde öğeleri **Dosya** menüsü.  
  
##  <a name="_core_initializing_your_own_additions_to_these_classes"></a> Bu sınıfların kendi eklemeler başlatılıyor  
 Önceki rakamlarıyla Ayrıca, uygulamanızın nesneleri başlatmak için üye işlevlerini geçersiz kılabilirsiniz noktaları öneririz. Geçersiz kılma `OnInitialUpdate` görünümünüzde sınıfı görünümü başlatmak için en iyi yerdir. `OnInitialUpdate` Çağrısı hemen çerçeve penceresi oluşturulur ve çerçeve penceresi görünümde, belgeye iliştirilmiş sonra oluşur. Örneğin, görünümünüzde kaydırma görünüm ise (türetilmiş `CScrollView` yerine `CView`), belge boyutu göre görünüm boyutu ayarlamanız gerekir, `OnInitialUpdate` geçersiz kıl. (Bu işlem sınıfı açıklamasında açıklanan [CScrollView](../mfc/reference/cscrollview-class.md).) Geçersiz kılabilirsiniz **CDocument** üye işlevleri `OnNewDocument` ve `OnOpenDocument` uygulamaya özgü başlatma belgenin sağlamak için. Genellikle, bir belge iki şekilde oluşturulabilir bu yana her ikisi de geçersiz kılmalısınız.  
  
 Çoğu durumda, temel sınıf sürümü geçersiz kılma çağırmalıdır. Adlandırılmış üye işlevleri sınıfların daha fazla bilgi için bkz [CDocument](../mfc/reference/cdocument-class.md), [CView](../mfc/reference/cview-class.md), [CFrameWnd](../mfc/reference/cframewnd-class.md), ve [CWinApp](../mfc/reference/cwinapp-class.md) MFC'de Kitaplık Başvurusu.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Belge şablonları ve belge/görünüm oluşturma işlemi](../mfc/document-templates-and-the-document-view-creation-process.md)   
 [Belge şablonu oluşturma](../mfc/document-template-creation.md)   
 [Belge/görünüm oluşturma](../mfc/document-view-creation.md)   
 [FC Nesneleri Arasındaki İlişki](../mfc/relationships-among-mfc-objects.md)

