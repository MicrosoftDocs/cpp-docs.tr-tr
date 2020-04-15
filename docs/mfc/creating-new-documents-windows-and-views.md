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
ms.openlocfilehash: aa1c58b02df92d79ca9915032b97fb5c0e2eaffc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371674"
---
# <a name="creating-new-documents-windows-and-views"></a>Yeni Belgeler, Pencereler ve Görünümler Oluşturma

Aşağıdaki şekiller, belgeler, görünümler ve çerçeve pencereleri için oluşturma işlemine genel bir bakış sağlar. Katılımcı nesnelere odaklanan diğer makaleler daha fazla ayrıntı sağlar.

Bu işlem tamamlandıktan sonra, işbirliği nesneleri var ve birbirlerine işaretçiler ilerler. Aşağıdaki şekiller nesnelerin oluşturulduğu sırayı gösterir. Şekil'den rakama sırayı takip edebilirsiniz.

![Belge oluşturma sırası](../mfc/media/vc387l1.gif "Belge oluşturma sırası") <br/>
Belge Oluşturmasırası

![Çerçeve Penceresi Oluşturma Sırası](../mfc/media/vc387l2.png "Çerçeve Penceresi Oluşturma Sırası") <br/>
Çerçeve Penceresi Oluşturmasırası

![Görünüm oluşturmak için sıra](../mfc/media/vc387l3.gif "Görünüm oluşturmak için sıra") <br/>
Görünüm Oluşturmada Sıra

Çerçevenin yeni belgeyi, görünümü ve çerçeve pencere nesnelerini nasıl başlattırışları hakkında bilgi için, MFC Kitaplığı Başvurusu'nda [CDocument](../mfc/reference/cdocument-class.md), [CView](../mfc/reference/cview-class.md), [CFrameWnd](../mfc/reference/cframewnd-class.md), [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md)ve [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md) sınıflarına bakın. Ayrıca, **Dosya** menüsündeki **Yeni** ve **Aç** öğeleri için çerçevenin standart komutlarını tartışması altında oluşturma ve başlatma işlemlerini daha da açıklayan Teknik [Not 22'ye](../mfc/tn022-standard-commands-implementation.md)bakın.

## <a name="initializing-your-own-additions-to-these-classes"></a><a name="_core_initializing_your_own_additions_to_these_classes"></a>Bu Sınıflara Kendi Eklemelerinizi Başlatma

Önceki rakamlar, uygulamanızın nesnelerini başlatmak için üye işlevleri geçersiz kılabileceğiniz noktaları da önerir. Görünüm `OnInitialUpdate` sınıfınızdaki geçersiz kılma, görünümü başlatmanın en iyi yeridir. Arama, `OnInitialUpdate` çerçeve penceresi oluşturulduktan ve çerçeve penceresi içindeki görünüm belgesine iliştirildikten hemen sonra gerçekleşir. Örneğin, görünümünüz bir kaydırma görünümüyse `CScrollView` (yerine `CView`türetilmişse), görünüm boyutunu geçersiz `OnInitialUpdate` kılmanızdaki belge boyutuna göre ayarlamanız gerekir. (Bu işlem [CScrollView](../mfc/reference/cscrollview-class.md)sınıfının açıklamasında açıklanmıştır.) `CDocument` Üye işlevleri `OnNewDocument` geçersiz kılabilir `OnOpenDocument` ve belgenin uygulamaya özgü başlatılmasını sağlayabilirsiniz. Genellikle, bir belge iki şekilde oluşturulabilir beri her ikisini de geçersiz kılmanız gerekir.

Çoğu durumda, geçersiz kılmanız taban sınıf sürümünü aramalıdır. Daha fazla bilgi için, MFC Kitaplık Başvurusu'nda [CDocument](../mfc/reference/cdocument-class.md), [CView](../mfc/reference/cview-class.md), [CFrameWnd](../mfc/reference/cframewnd-class.md)ve [CWinApp](../mfc/reference/cwinapp-class.md) sınıflarının adlandırılmış üye işlevlerine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Belge Şablonları ve Belge/Görünüm Oluşturma İşlemi](../mfc/document-templates-and-the-document-view-creation-process.md)<br/>
[Belge Şablonu Oluşturma](../mfc/document-template-creation.md)<br/>
[Belge/Görünüm Oluşturma](../mfc/document-view-creation.md)<br/>
[MFC Nesneleri Arasındaki İlişki](../mfc/relationships-among-mfc-objects.md)
