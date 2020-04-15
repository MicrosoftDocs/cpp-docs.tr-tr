---
title: 'TN025: Belge, Görünüm ve Çerçeve Oluşturma'
ms.date: 11/04/2016
f1_keywords:
- vc.creation
helpviewer_keywords:
- documents [MFC], view and frame creation
- TN025
ms.assetid: 09254d72-6e1d-43db-80e9-693887dbeda2
ms.openlocfilehash: 2fdabdcb1a87d4a5661348588d49303290c966ce
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370366"
---
# <a name="tn025-document-view-and-frame-creation"></a>TN025: Belge, Görünüm ve Çerçeve Oluşturma

> [!NOTE]
> Aşağıdaki teknik not, çevrimiçi belgelere ilk olarak eklenmediğinden beri güncelleştirilemedi. Sonuç olarak, bazı yordamlar ve konular güncel veya yanlış olabilir. En son bilgiler için, çevrimiçi belge dizini ilgi alanı için arama nız önerilir.

Bu not, WinApps, DocTemplates, Belgeler, Çerçeveler ve Görünümler için oluşturma ve sahiplik sorunlarını açıklar.

## <a name="winapp"></a>WinApp

Sistemde bir `CWinApp` nesne var.

Statik olarak inşa edilmiş ve çerçevenin iç uygulaması `WinMain`ile başharf. Yararlı bir şey `CWinApp` yapmak için türetmeniz gerekir (özel durum: MFC uzantısı DLL'lerin bir `CWinApp` örneği olmamalıdır — bunun `DllMain` yerine başlatma yapılır).

Tek `CWinApp` nesne belge şablonları listesine `CPtrList`(a) sahip. Uygulama başına bir veya daha fazla belge şablonu vardır. DocTemplates genellikle kaynak dosyasından (yani bir dize `CWinApp::InitInstance`dizisinden) yüklenir.

```
pTemplate = new CDocTemplate(IDR_MYDOCUMENT, ...);

AddDocTemplate(pTemplate);
```

Tek `CWinApp` nesne, uygulamadaki tüm çerçeve pencerelerine sahiptir. Uygulamanın ana çerçeve penceresi içinde `CWinApp::m_pMainWnd`depolanmalıdır; appwizard *m_pMainWnd* sizin için `InitInstance` bunu izin vermediyseniz genellikle uygulamada m_pMainWnd ayarlayın. Tek belge arabirimi (SDI) `CFrameWnd` için bu, ana uygulama çerçevesi penceresi nin yanı sıra tek belge çerçevesi penceresi olarak hizmet veren bir tanesidir. Birden çok belge arabirimi (MDI) için bu, tüm alt `CMDIFrameWnd` `CFrameWnd`s içeren ana uygulama çerçevesi penceresi olarak hizmet veren bir MDI-Frame (sınıf) olduğunu. Her alt pencere `CMDIChildWnd` sınıf `CFrameWnd`(türetilmiş) ve potansiyel olarak çok sayıda belge çerçeve pencerelerinden biri olarak hizmet vermektedir.

## <a name="doctemplates"></a>Doküman Şablonları

Belgelerin `CDocTemplate` yaratıcısı ve yöneticisidir. Oluşturduğu belgelerin sahibidir. Uygulamanız aşağıda açıklanan kaynak tabanlı yaklaşımı kullanıyorsa, 'den `CDocTemplate`türemesi gerekmez.

Bir SDI uygulaması için `CSingleDocTemplate` sınıf bir açık belgeyi izler. Bir MDI uygulaması için `CMultiDocTemplate` sınıf, bu `CPtrList`şablondan oluşturulan şu anda açık olan tüm belgelerin listesini (a) tutar. `CDocTemplate::AddDocument`ve `CDocTemplate::RemoveDocument` belgeeklemek veya şablondan kaldırmak için sanal üye işlevleri sağlayın. `CDocTemplate`belgeyi oluşturan `CDocument` doküman şablonuna `CDocument::m_pDocTemplate` geri dönecek şekilde korumalı geri işaretçisini ayarlayabilmemiz için bir arkadaştır.

`CWinApp`sırayla tüm `OnFileOpen` doküman şablonlarını sorgulayacak varsayılan uygulamayı işler. Uygulama, zaten açık olan belgeleri aramayı ve yeni belgeleri hangi biçimde açacağınızkonusunda karar mayı içerir.

`CDocTemplate`belgeler ve çerçeveler için UI bağlamayı yönetir.

`CDocTemplate`adı açıklanmayan belge sayısının sayısını tutar.

## <a name="cdocument"></a>Cdocument

A' `CDocument` nın `CDocTemplate`sahibi olduğu bir .

Belgeler, belgeyi (a) `CView` `CPtrList`görüntüleyen şu anda açık olan görünümlerin (türetilmiş) bir listesine sahiptir.

Belgeler görünümoluşturmaz/yok etmez, ancak oluşturulduktan sonra birbirlerine bağlanır. Bir belge kapatıldığında (diğer bir şekilde Dosya/Kapat aracılığıyla), eklenen tüm görünümler kapatılır. Belgedeki son görünüm kapatıldığında (diğer bir şekilde Pencere/Kapat) belge kapatılır.

`CDocument::AddView`, `RemoveView` arabirim görünüm listesini korumak için kullanılır. `CDocument`bir `CView` arkadaş, bu yüzden `CView::m_pDocument` geri işaretçi ayarlayabilirsiniz.

## <a name="cframewnd"></a>CFrameWnd

A `CFrameWnd` (çerçeve olarak da bilinir) MFC 1.0 ile aynı `CFrameWnd` rolü oynar, ancak şimdi sınıf yeni bir sınıf türelemeden birçok durumda kullanılmak üzere tasarlanmıştır. Türetilen `CMDIFrameWnd` sınıflar `CMDIChildWnd` ve aynı zamanda birçok standart komutları zaten uygulanmaktadır geliştirilmiştir.

Çerçevenin `CFrameWnd` istemci alanında pencere oluşturmaktan sorumludur. Normalde çerçevenin istemci alanını dolduran bir ana pencere vardır.

Bir MDI-Frame penceresi için istemci alanı, tüm MDI-Child çerçeve pencerelerinin üst öğesi olan MDICLIENT denetimiyle doldurulur. Bir SDI-Frame penceresi veya MDI-Alt çerçeve penceresi için istemci `CView`alanı genellikle türetilmiş bir pencere nesnesi ile doldurulur. Durumunda `CSplitterWnd`, görünümün istemci alanı `CSplitterWnd` pencere nesnesi ile doldurulur ve `CView`türetilmiş pencere nesneleri (bölünmüş bölme başına `CSplitterWnd`bir) alt pencere olarak oluşturulur.

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya Göre Teknik Notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)
