---
title: 'TN025: Belge, Görünüm ve çerçeve oluşturma'
ms.date: 11/04/2016
f1_keywords:
- vc.creation
helpviewer_keywords:
- documents [MFC], view and frame creation
- TN025
ms.assetid: 09254d72-6e1d-43db-80e9-693887dbeda2
ms.openlocfilehash: 4958e7c4ca2c3cf9eed6420d72d0399fa112098d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62306002"
---
# <a name="tn025-document-view-and-frame-creation"></a>TN025: Belge, Görünüm ve çerçeve oluşturma

> [!NOTE]
>  Aşağıdaki Teknik Not çevrimiçi belgelere ilk eklenmiştir beri güncelleştirilmemiş. Eski veya yanlış sonuç olarak, bazı yordamlar ve konular olabilir. En son bilgiler için bu konuyu çevrimiçi belge dizininde arama önerilir.

Bu Not, WinApps, DocTemplates, belgeler, çerçeveler ve görünümler oluşturma ve sahiplik sorunlarını açıklar.

## <a name="winapp"></a>WinApp

Bir `CWinApp` sistem nesnesi.

Bu statik olarak oluşturulur ve framework'ün iç uygulaması tarafından başlatılan `WinMain`. Öğesinden türetilmelidir `CWinApp` faydalı bir şey için (özel durum: MFC uzantı DLL'leri olmamalıdır bir `CWinApp` örneği — başlatma gerçekleştirilir `DllMain` yerine).

Bir `CWinApp` nesneye sahip bir belge şablonları listesi (bir `CPtrList`). Uygulama başına bir veya birden çok belge şablonu yoktur. DocTemplates genellikle yüklenir (diğer bir deyişle, bir dize dizisi) kaynak dosyasından `CWinApp::InitInstance`.

```
pTemplate = new CDocTemplate(IDR_MYDOCUMENT, ...);

AddDocTemplate(pTemplate);
```

Bir `CWinApp` nesneye sahip tüm çerçeve pencereleri uygulama. Ana çerçeve penceresidir depolanması gereken `CWinApp::m_pMainWnd`; genellikle ayarladığınız *m_pMainWnd* içinde `InitInstance` sizin yerinize yapmasını AppWizard bulunmamasını, uygulama. Tek Belgeli Arabirim (SDI) için bu biridir `CFrameWnd` yalnızca belge çerçeve penceresi yanı sıra uygulamanın ana çerçeve penceresi sunar. Birden Çok Belgeli Arabirim (MDI) için bir MDI çerçeve budur (sınıfı `CMDIFrameWnd`) tüm alt içeren ana uygulama çerçeve penceresi hizmet veren `CFrameWnd`s. Her alt penceresi sınıfıdır `CMDIChildWnd` (türetilen `CFrameWnd`) ve potansiyel olarak birçok belge çerçeve pencereleri biri olarak görev yapar.

## <a name="doctemplates"></a>DocTemplates

`CDocTemplate` Oluşturan ve belgelerin yöneticisidir. Oluşturduğu belgeler sahibidir. Uygulamanız aşağıda açıklanan kaynak tabanlı yaklaşımı kullanıyorsa, türetilen gerekmez `CDocTemplate`.

Sınıfı bir SDI uygulaması `CSingleDocTemplate` açık bir belge izler. Bir MDI uygulaması sınıfı için `CMultiDocTemplate` listesini tutar (bir `CPtrList`) Bu şablondan oluşturulan tüm açık belgeleri. `CDocTemplate::AddDocument` ve `CDocTemplate::RemoveDocument` sanal üye ekleme veya bir belge şablonu kaldırmak için işlevleri sağlar. `CDocTemplate` bir arkadaşınız, `CDocument` böylece biz korumalı ayarlayabilirsiniz `CDocument::m_pDocTemplate` geri belgeyi oluşturan belge şablonu için işaret edecek şekilde geri işaretçisi.

`CWinApp` varsayılan işleme `OnFileOpen` uygulama, tüm belge şablonları sırayla sorgular. Uygulama zaten açık belgeleri mi arıyorsunuz ve yeni belgeleri açmak için hangi biçimi karar içerir.

`CDocTemplate` belgeler ve çerçeveler için kullanıcı Arabirimi bağlama yönetir.

`CDocTemplate` Adsız belgelerin sayısını tutar.

## <a name="cdocument"></a>CDocument

A `CDocument` tarafından sahip olunan bir `CDocTemplate`.

Belgeleriniz görünümleri açık bir listesini (türetilen `CView`) belge görüntüleme (bir `CPtrList`).

Belgeleri oluşturun/görünümler yok değil, ancak oluşturulduktan sonra birbirine bağlı. Bir belge kapatıldığı (diğer bir deyişle, ile Dosya/Kapat), ekli tüm görünümlere kapatılacak. Bir belgeyi son görünümü kapalı olduğunda (diğer bir deyişle, pencere/Kapat) belge kapatılacak.

`CDocument::AddView`, `RemoveView` Arabirimi görünüm listesini korumak için kullanılır. `CDocument` bir arkadaşınız, `CView` ayarlayabilirsiniz bu nedenle `CView::m_pDocument` geri işaretçisi.

## <a name="cframewnd"></a>CFrameWnd

A `CFrameWnd` (çerçeve olarak da bilinir) ancak şimdi MFC 1.0, olduğu gibi aynı rol oynar `CFrameWnd` sınıfı çoğu durumda, yeni bir sınıf türetmek olmadan kullanılmak üzere tasarlanmıştır. Türetilen sınıfların `CMDIFrameWnd` ve `CMDIChildWnd` birçok standart komut zaten uygulanmış şekilde de geliştirilmiştir.

`CFrameWnd` Çerçevenin istemci alanının windows oluşturmaktan sorumludur. Normalde çerçevenin istemci alanını dolduran bir ana penceresi yok.

Bir MDI çerçeve penceresi tüm MDI alt çerçeve Pencereleri üst sırayla olan MDICLIENT denetimi ile istemci alanını doldurulur. Bir SDI çerçeve penceresinin veya MDI alt çerçeve için istemci alanını genellikle renkle doldurulup bir `CView`-türetilmiş pencere nesnesi. Durumunda, `CSplitterWnd`, görünüm istemci alanının doldurulup `CSplitterWnd` pencere nesnesi ve `CView`-türetilen pencere nesneleri (tek başına parçalı bölme) alt pencereler gibi oluşturulur `CSplitterWnd`.

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya Göre Teknik Notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)
