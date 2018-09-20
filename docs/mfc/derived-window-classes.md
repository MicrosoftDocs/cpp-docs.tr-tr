---
title: Türetilen pencere sınıfları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- window class hierarchy
- hierarchies, window classes
- classes [MFC], derived
- CWnd class [MFC], classes derived from
- derived classes [MFC], window classes
- window classes [MFC], derived
ms.assetid: 6f7e437e-fbde-4a06-bfab-72d9dbf05292
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2840a78844f42481389ba868b6ab1bc5713a2c0b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46448019"
---
# <a name="derived-window-classes"></a>Türetilen Pencere Sınıfları

Doğrudan windows oluşturabilirsiniz [CWnd](../mfc/reference/cwnd-class.md), ya da yeni pencere sınıflarından `CWnd`. Kendi özel pencerelerinizi genellikle oluşturma budur. Ancak, bir çerçeve programında kullanılan çoğu pencere yerine birinden oluşturulan `CWnd`-türetilmiş MFC tarafından sağlanan çerçeve pencere sınıfları.

## <a name="frame-window-classes"></a>Çerçeve penceresi sınıfları

[CFrameWnd](../mfc/reference/cframewnd-class.md)<br/>
Tek bir belge ve onun görünümünü çerçeveleyen SDI çerçeve pencereleri için kullanılır. Çerçeve penceresi hem uygulamanın ana çerçeve penceresi hem de geçerli belgenin çerçeve penceresinin ' dir.

[CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md)<br/>
MDI uygulamaları için ana çerçeve penceresi olarak kullanılır. Ana çerçeve penceresi tüm MDI belge pencerelerini kapsayıcısıdır ve bunlarla menü çubuğunu paylaşır. Bir MDI çerçeve penceresi masaüstünde beliren bir üst düzey bir penceredir.

[Cmdıchildwnd](../mfc/reference/cmdichildwnd-class.md)<br/>
Bir MDI ana çerçeve penceresinde açılan tek tek belgeler için kullanılır. Her belge ve onun görünümü, MDI ana çerçeve penceresi tarafından içerdiği bir MDI alt çerçeve penceresi tarafından çerçevelidir. Bir MDI alt penceresi çok tipik bir çerçeve penceresi gibi görünür ancak Masaüstü yerine bir MDI çerçeve penceresinin içinde bulunur. Ancak, MDI alt penceresinin kendi menü çubuğu eksik ve onu içeren MDI çerçeve penceresinin menü çubuğunu paylaşmalıdır.

Daha fazla bilgi için [çerçeve Windows](../mfc/frame-windows.md).

## <a name="other-window-classes-derived-from-cwnd"></a>CWnd'den türetilen diğer pencere sınıfları

Çerçeve pencereleri çerçevelemenin yanı sıra çeşitli diğer başlıca birçok kategorisi öğesinden türetilen `CWnd`:

*Görünümler*<br/>
Görünümleri kullanarak oluşturulan `CWnd`-türetilmiş sınıf [CView](../mfc/reference/cview-class.md) (veya ondan türetilen sınıflardan biri). Bir görünümü, bir belgeye ekli ve belge ile kullanıcı arasında aracı görevi görür. Genellikle bir SDI çerçeve penceresinin veya MDI alt çerçeve penceresi (veya bir araç çubuğu ve/veya durum çubuğu tarafından kapsanmayan istemci alanının bu bölümü) istemci alanını dolduran bir alt pencere (MDI alt değil) bir görünümüdür.

*İletişim Kutuları*<br/>
İletişim kutusu kullanılarak oluşturulur `CWnd`-türetilmiş sınıf [CDialog](../mfc/reference/cdialog-class.md).

*Formlar*<br/>
İletişim kutuları gibi iletişim şablonu kaynaklarına dayalı form görünümleri, sınıflar kullanılarak oluşturulur [CFormView](../mfc/reference/cformview-class.md), [CRecordView](../mfc/reference/crecordview-class.md), veya [CDaoRecordView](../mfc/reference/cdaorecordview-class.md).

*Denetimler*<br/>
Düğmeler, liste kutuları ve birleşik giriş kutuları gibi denetimler, türetilen diğer sınıflar kullanılarak oluşturulur `CWnd`. Bkz: [kontrol konuları](../mfc/controls-mfc.md).

*Denetim Çubukları*<br/>
Denetimler içeren alt pencereler. Örnekler, araç çubuklarını ve durum çubuklarını içerir. Bkz: [denetim çubukları](../mfc/control-bars.md).

## <a name="window-class-hierarchy"></a>Pencere sınıfı hiyerarşisi

Başvurmak [MFC hiyerarşisi grafiği](../mfc/hierarchy-chart.md) içinde *MFC başvurusu*. Görünümler içinde açıklanan [belge/görünüm mimarisi](../mfc/document-view-architecture.md). İletişim kutuları içinde açıklanan [iletişim kutuları](../mfc/dialog-boxes.md).

## <a name="creating-your-own-special-purpose-window-classes"></a>Kendi özel amaçlı pencere sınıflarınızı oluşturma

Sınıf kitaplığının verdiği pencere sınıflarının yanı sıra özel amaçlı alt pencereler gerekebilir. Böyle bir pencere oluşturmak için kendi oluşturun [CWnd](../mfc/reference/cwnd-class.md)-türetilmiş sınıf ve bir çerçeve veya görünümün alt penceresi yapın. Framework bir belge çerçevesi penceresinin istemci alanı kapsamını yönettiğini aklınızda size aittir. İstemci alanlarının çoğu bir görünüm, ancak diğer windows tarafından yönetilen, gibi denetim çubukları veya kendi özel pencerelerinizi alanı paylaşabilir görünümüyle. Sınıflarındaki mekanizmalarla etkileşimde bulunmanız gerekebilir [CView](../mfc/reference/cview-class.md) ve [CControlBar](../mfc/reference/ccontrolbar-class.md) alt pencereleri bir çerçeve penceresinin istemci alanına konumlandırma için.

[Windows oluşturma](../mfc/creating-windows.md) oluşturulmasını pencere nesneleri ve yönettikleri pencereler anlatılmaktadır.

## <a name="see-also"></a>Ayrıca Bkz.

[Pencere Nesneleri](../mfc/window-objects.md)

