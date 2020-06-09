---
title: Türetilen Pencere Sınıfları
ms.date: 11/04/2016
helpviewer_keywords:
- window class hierarchy
- hierarchies, window classes
- classes [MFC], derived
- CWnd class [MFC], classes derived from
- derived classes [MFC], window classes
- window classes [MFC], derived
ms.assetid: 6f7e437e-fbde-4a06-bfab-72d9dbf05292
ms.openlocfilehash: c84284b765e740fa0a13972e9902e7737e15bbab
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84623170"
---
# <a name="derived-window-classes"></a>Türetilen Pencere Sınıfları

Windows 'u doğrudan [CWnd](reference/cwnd-class.md)'den oluşturabilir veya yeni pencere sınıflarını öğesinden türetebilirsiniz `CWnd` . Bu, genellikle kendi özel pencerelerini oluşturur. Ancak, bir çerçeve programında kullanılan çoğu pencere, `CWnd` MFC tarafından sağlanan türetilmiş çerçeve pencere sınıflarından biri tarafından oluşturulur.

## <a name="frame-window-classes"></a>Çerçeve penceresi sınıfları

[CFrameWnd](reference/cframewnd-class.md)<br/>
Tek bir belgeyi ve görünümünü gösteren SDI çerçeve pencereleri için kullanılır. Çerçeve penceresi, uygulamanın ana çerçeve penceresi ve geçerli belge için çerçeve penceresidir.

[CMDIFrameWnd](reference/cmdiframewnd-class.md)<br/>
MDI uygulamaları için ana çerçeve penceresi olarak kullanılır. Ana çerçeve penceresi tüm MDI belge pencereleri için bir kapsayıcıdır ve onun menü çubuğunu kendileriyle paylaşır. MDI çerçevesi penceresi, masaüstünde görüntülenen bir üst düzey penceredir.

[CMDIChildWnd](reference/cmdichildwnd-class.md)<br/>
MDI ana çerçeve penceresinde açılan bireysel belgeler için kullanılır. Her belge ve görünümü MDI ana çerçeve penceresinin içerdiği bir MDI alt çerçeve penceresi tarafından çerçevelenmiş. MDI alt penceresi, tipik bir çerçeve penceresi gibi görünür, ancak masaüstünde oturmek yerine MDI çerçevesi penceresi içinde yer alır. Ancak, MDI alt penceresinde kendi menü çubuğu yoktur ve bunu içeren MDI çerçeve penceresinin menü çubuğunu paylaşmalıdır.

Daha fazla bilgi için bkz. [çerçeve pencereleri](frame-windows.md).

## <a name="other-window-classes-derived-from-cwnd"></a>CWnd 'den türetilmiş diğer pencere sınıfları

Çerçeve pencerelerinin yanı sıra, Windows 'un diğer birçok büyük kategorisi şu kaynaktan türetilir `CWnd` :

*Görünümler*<br/>
Görünümler `CWnd` -türetilmiş sınıf [CView](reference/cview-class.md) (veya türetilen sınıflarından biri) kullanılarak oluşturulur. Bir görünüm belgeye iliştirilir ve belge ve Kullanıcı arasında bir aracı görevi görür. Bir görünüm, genellikle bir SDI çerçeve penceresinin veya bir MDI alt çerçeve penceresinin (ya da bir araç çubuğu ile/veya bir durum çubuğu tarafından kapsanmayan istemci alanının bir bölümü) istemci alanını dolduran bir alt penceredir (MDI alt öğesi değil).

*İletişim Kutuları*<br/>
İletişim kutuları `CWnd` -türetilmiş sınıf [CDialog](reference/cdialog-class.md)kullanılarak oluşturulur.

*Formlar*<br/>
İletişim kutuları gibi iletişim kutusu şablon kaynaklarına dayanan form görünümleri [CFormView](reference/cformview-class.md), [CRecordView](reference/crecordview-class.md)veya [CDaoRecordView](reference/cdaorecordview-class.md)sınıfları kullanılarak oluşturulur.

*Denetimler*<br/>
Düğmeler, liste kutuları ve Birleşik giriş kutuları gibi denetimler, öğesinden türetilmiş diğer sınıflar kullanılarak oluşturulur `CWnd` . Bkz. [Denetim konuları](controls-mfc.md).

*Denetim Çubukları*<br/>
Denetimleri içeren alt pencereler. Araç çubukları ve durum çubukları örnekleri içerir. Bkz. [Denetim çubukları](control-bars.md).

## <a name="window-class-hierarchy"></a>Pencere sınıfı hiyerarşisi

*MFC başvurusunda* [MFC hiyerarşi grafiğine](hierarchy-chart.md) bakın. Görünümler [belge/görünüm mimarisinde](document-view-architecture.md)açıklanmıştır. İletişim kutuları [Iletişim kutularında](dialog-boxes.md)açıklanmaktadır.

## <a name="creating-your-own-special-purpose-window-classes"></a>Kendi özel amaçlı pencere sınıflarınızı oluşturma

Sınıf kitaplığı tarafından sunulan pencere sınıflarının yanı sıra, özel amaçlı alt pencereler de gerekebilir. Böyle bir pencere oluşturmak için kendi [CWnd](reference/cwnd-class.md)-türetilmiş sınıfınızı oluşturun ve bir çerçevenin ya da görünümün alt penceresi yapın. Çerçevenin bir belge çerçevesi penceresinin istemci alanının kapsamını yönettiğini göz önünde bulundurun. İstemci alanının çoğu bir görünüm tarafından yönetilir, ancak denetim çubukları veya kendi özel pencereleri gibi diğer pencereler, alanı görünümle paylaşabilir. Bir çerçeve penceresinin istemci alanındaki alt pencereleri konumlandırmak için [CView](reference/cview-class.md) ve [CControlBar](reference/ccontrolbar-class.md) sınıflardaki mekanizmalarla etkileşimde bulunmak gerekebilir.

[Windows oluşturma](creating-windows.md) , pencere nesnelerinin ve yönettikleri pencerelerin oluşturulmasını açıklar.

## <a name="see-also"></a>Ayrıca bkz.

[Pencere nesneleri](window-objects.md)
