---
title: Yeni Belgeler, Pencereler ve Görünümler Oluşturma
ms.date: 11/19/2018
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
ms.openlocfilehash: 3d4ca55a9bff6ec42643db745896a2cea96dcefb
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57297817"
---
# <a name="creating-new-documents-windows-and-views"></a>Yeni Belgeler, Pencereler ve Görünümler Oluşturma

Aşağıdaki şekilde, belgeler, görünümler ve çerçeve pencereleri oluşturma işlemine genel bakış sağlar. Katılımcı nesneler üzerinde odaklanın diğer makaleleri daha ayrıntılı bilgiler sağlar.

Bu işlem tamamlandıktan sonra birlikte çalışan nesnelerin var ve birbirlerine işaretçileri depolayın. Aşağıdaki şekil, nesnelerin oluşturulduğu sıranın gösterir. Şekil şekil dizisi takip edebilirsiniz.

![Bir belge oluşturmak için dizisi](../mfc/media/vc387l1.gif "sıralı bir belge oluşturmak için") <br/>
Bir belge oluşturma sırası

![Çerçeve pencere oluşturma dizisi](../mfc/media/vc387l2.png "çerçeve pencere oluşturma dizisi") <br/>
Çerçeve pencere oluşturma dizisi

![Görünüm oluşturmayla ilgili dizisini](../mfc/media/vc387l3.gif "sırası bir görünüm oluşturmak için") <br/>
Bir görünüm oluşturma sırası

Sınıfları nasıl yeni bir belge, Görünüm ve çerçeve pencere nesneleri framework başlatır hakkında daha fazla bilgi için bkz. [CDocument](../mfc/reference/cdocument-class.md), [CView](../mfc/reference/cview-class.md), [CFrameWnd](../mfc/reference/cframewnd-class.md), [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md), ve [Cmdıchildwnd](../mfc/reference/cmdichildwnd-class.md) MFC Kitaplığı Başvurusu. Ayrıca bkz: [Teknik Not 22](../mfc/tn022-standard-commands-implementation.md), açıklayan oluşturma ve başlatma işlemleri daha fazla framework'ün standart komut için kendi tartışma altında **yeni** ve **açın** üzerinde öğelerini **dosya** menüsü.

##  <a name="_core_initializing_your_own_additions_to_these_classes"></a> Bu sınıfların kendi eklemeleri başlatılıyor

Önceki rakamları Ayrıca, uygulamanızın nesneleri, üye işlevleri geçersiz kılabilirsiniz noktaları önerilir. Geçersiz kılma `OnInitialUpdate` görünümünüzde sınıf görünümü başlatmak için en iyi yerdir. `OnInitialUpdate` Çağrı hemen çerçeve penceresi oluşturulur ve görünümü çerçeve penceresi içinde belgeye eklendikten sonra gerçekleşir. Örneğin, kaydırma görünümü, görünüm ise (türetilen `CScrollView` yerine `CView`), belge boyutunu temel görünüm boyutu ayarlamanız gerekir, `OnInitialUpdate` geçersiz. (Bu işlemin sınıf açıklamasında açıklanan [CScrollView](../mfc/reference/cscrollview-class.md).) Geçersiz kılabilirsiniz `CDocument` üye işlevleri `OnNewDocument` ve `OnOpenDocument` uygulamaya özgü belgeyi başlangıcına sağlamak için. Bir belge iki şekilde oluşturulabilir beri genellikle, her ikisi de geçersiz kılmanız gerekir.

Çoğu durumda, geçersiz kılma temel sınıftaki sürümün çağırmalıdır. Daha fazla bilgi için bkz: sınıflar adlandırılan üye işlevleri [CDocument](../mfc/reference/cdocument-class.md), [CView](../mfc/reference/cview-class.md), [CFrameWnd](../mfc/reference/cframewnd-class.md), ve [CWinApp](../mfc/reference/cwinapp-class.md) MFC'de Kitaplık Başvurusu.

## <a name="see-also"></a>Ayrıca bkz.

[Belge şablonları ve belge/görünüm oluşturma işlemi](../mfc/document-templates-and-the-document-view-creation-process.md)<br/>
[Belge Şablonu Oluşturma](../mfc/document-template-creation.md)<br/>
[Belge/görünüm oluşturma](../mfc/document-view-creation.md)<br/>
[FC Nesneleri Arasındaki İlişki](../mfc/relationships-among-mfc-objects.md)
