---
description: 'Daha fazla bilgi edinin: yeni belgeler, pencereler ve görünümler oluşturma'
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
ms.openlocfilehash: 718d24d63811d4e3b5cc847b5d0ef69361c6fdf3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97309881"
---
# <a name="creating-new-documents-windows-and-views"></a>Yeni Belgeler, Pencereler ve Görünümler Oluşturma

Aşağıdaki rakamlar belgeler, görünümler ve çerçeve pencereleri için oluşturma sürecine genel bir bakış sunar. Katılan nesnelere odaklanmakta olan diğer makaleler daha fazla ayrıntı sağlar.

Bu işlemi tamamladıktan sonra, birlikte çalışan nesneler bulunur ve işaretçileri birbirlerine depolar. Aşağıdaki rakamlar, nesnelerin oluşturulduğu sırayı gösterir. Şekil 'den şekle kadar sırayı izleyebilirsiniz.

![Belge oluşturmak için sıra](../mfc/media/vc387l1.gif "Belge oluşturmak için sıra") <br/>
Belge oluşturma sırası

![Çerçeve penceresi oluşturma sırası](../mfc/media/vc387l2.png "Çerçeve penceresi oluşturma sırası") <br/>
Çerçeve penceresi oluşturma sırası

![Görünüm oluşturmak için sıra](../mfc/media/vc387l3.gif "Görünüm oluşturmak için sıra") <br/>
Görünüm oluşturma sırasında sıra

Framework 'ün yeni belge, görünüm ve çerçeve pencere nesnelerini nasıl Başlatan hakkında daha fazla bilgi için, MFC Kitaplığı başvurusunda [CDocument](reference/cdocument-class.md), [CView](reference/cview-class.md), [CFrameWnd](reference/cframewnd-class.md), [Cmdiframewnd](reference/cmdiframewnd-class.md)ve [cmdictepdınd](reference/cmdichildwnd-class.md) sınıflarını inceleyin. Ayrıca, oluşturma ve başlatma işlemlerinin, **Dosya** menüsündeki **Yeni** ve **Açık** öğeler için Framework 'ün standart komutları tartışmasından daha da [ayrıntılı olarak açıklanmaktadır](tn022-standard-commands-implementation.md).

## <a name="initializing-your-own-additions-to-these-classes"></a><a name="_core_initializing_your_own_additions_to_these_classes"></a> Bu sınıflara kendi eklemelerinizi başlatma

Yukarıdaki rakamlar, uygulamanızın nesnelerini başlatmak için üye işlevlerini geçersiz kılabileceğiniz noktaları da önerir. Görünüm sınıfınıza ilişkin bir geçersiz kılma, `OnInitialUpdate` görünümü başlatmak için en iyi yerdir. `OnInitialUpdate`Çağrı, çerçeve penceresi oluşturulduktan sonra ve çerçeve penceresi içindeki görünüm belgeye İliştirildikten hemen sonra gerçekleşir. Örneğin, görünümelde bir kaydırma görünümü varsa (yerine öğesinden türetilmiş `CScrollView` `CView` ), görünüm boyutunu geçersiz kılmanızda belge boyutuna göre ayarlamanız gerekir `OnInitialUpdate` . (Bu işlem, [CScrollView](reference/cscrollview-class.md)sınıfının açıklamasında açıklanmaktadır.) Üye işlevlerini geçersiz kılabilir `CDocument` `OnNewDocument` ve `OnOpenDocument` belgeyi uygulamaya özel olarak başlatmayı sağlayabilirsiniz. Genellikle, bir belgenin iki şekilde oluşturulabilmesinden bu yana her ikisini de geçersiz kılmanız gerekir.

Çoğu durumda, geçersiz kılma temel sınıf sürümünü çağırmalıdır. Daha fazla bilgi için, MFC kitaplık başvurusunda [CDocument](reference/cdocument-class.md), [CView](reference/cview-class.md), [CFrameWnd](reference/cframewnd-class.md)ve [CWinApp](reference/cwinapp-class.md) sınıflarının adlandırılmış üye işlevlerine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Belge şablonları ve belge/görünüm oluşturma Işlemi](document-templates-and-the-document-view-creation-process.md)<br/>
[Belge şablonu oluşturma](document-template-creation.md)<br/>
[Belge/görünüm oluşturma](document-view-creation.md)<br/>
[MFC nesneleri arasındaki ilişkiler](relationships-among-mfc-objects.md)
