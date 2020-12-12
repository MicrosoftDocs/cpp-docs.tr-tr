---
description: 'Daha fazla bilgi edinin: TN025: belge, görünüm ve çerçeve oluşturma'
title: 'TN025: Belge, Görünüm ve Çerçeve Oluşturma'
ms.date: 11/04/2016
f1_keywords:
- vc.creation
helpviewer_keywords:
- documents [MFC], view and frame creation
- TN025
ms.assetid: 09254d72-6e1d-43db-80e9-693887dbeda2
ms.openlocfilehash: 034c3670df57de03cf7db8f713937f3d433fbb56
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97215748"
---
# <a name="tn025-document-view-and-frame-creation"></a>TN025: Belge, Görünüm ve Çerçeve Oluşturma

> [!NOTE]
> Aşağıdaki teknik Not, çevrimiçi belgelere ilk eklenmesinden beri güncelleştirilmemiş. Sonuç olarak, bazı yordamlar ve konular güncel olmayabilir veya yanlış olabilir. En son bilgiler için çevrimiçi belge dizininde ilgilendiğiniz konuyu aramanız önerilir.

Bu notta, WinApps, DocTemplates, belgeler, çerçeveler ve görünümler için oluşturma ve sahiplik sorunları açıklanmaktadır.

## <a name="winapp"></a>WinApp

`CWinApp`Sistemde bir nesne vardır.

Statik olarak oluşturulur ve Framework 'ün iç uygulamasıyla başlatılır `WinMain` . ' Dan ' e türetmeniz gerekir `CWinApp` (özel durum: MFC uzantı dll 'leri bir örneğe sahip olmamalıdır `CWinApp` — başlatma bunun yerine ' de yapılır `DllMain` ).

Bir `CWinApp` nesne bir belge şablonları listesine sahip (a `CPtrList` ). Uygulama başına bir veya daha fazla belge şablonu var. DocTemplates genellikle ' de kaynak dosyasından (yani bir dize dizisi) yüklenir `CWinApp::InitInstance` .

```
pTemplate = new CDocTemplate(IDR_MYDOCUMENT, ...);

AddDocTemplate(pTemplate);
```

Bir `CWinApp` nesne, uygulamadaki tüm çerçeve pencerelerinin sahibi. Uygulamanın ana çerçeve penceresi ' de depolanmalıdır `CWinApp::m_pMainWnd` ; genellikle  `InitInstance` AppWizard 'ı sizin yerinize yapamadıysanız uygulamada m_pMainWnd ayarlarsınız. Tek belge arabirimi (SDI) için bu, `CFrameWnd` ana uygulama çerçevesi penceresi ve yalnızca belge çerçevesi penceresi olarak görev gören bir uygulamadır. Birden çok belge arabirimi (MDI) için bu, `CMDIFrameWnd` tüm alt öğeleri içeren ana uygulama çerçevesi penceresi olarak hizmet veren bir MDI-Frame (sınıf) `CFrameWnd` . Her bir alt pencere bir sınıftır `CMDIChildWnd` (öğesinden türetilir `CFrameWnd` ) ve potansiyel olarak çok sayıda belge çerçevesi penceresi işlevi görür.

## <a name="doctemplates"></a>DocTemplates

, `CDocTemplate` Belgelerinin Oluşturucusu ve yöneticisidir. Oluşturduğu belgelerin sahibi. Uygulamanız aşağıda açıklanan kaynak tabanlı yaklaşımı kullanıyorsa, ' den türetmeniz gerekmez `CDocTemplate` .

Bir SDI uygulaması için, sınıfı `CSingleDocTemplate` tek bir açık belgeyi izler. MDI uygulaması için, sınıfı `CMultiDocTemplate` `CPtrList` Bu şablondan oluşturulan Şu anda açık olan tüm belgelerin bir listesini (a) tutar. `CDocTemplate::AddDocument` ve `CDocTemplate::RemoveDocument` şablondan belge ekleme veya kaldırma için sanal üye işlevlerini sağlar. `CDocTemplate` , uygulamasının bir arkadaşınız ve `CDocument` `CDocument::m_pDocTemplate` belgeyi oluşturan belge şablonuna geri dönmek için korumalı geri işaretçiyi ayarlayabiliriz.

`CWinApp` varsayılan uygulamayı işler ve `OnFileOpen` Bu işlem, tüm belge şablonlarını sorgular. Uygulama, zaten açık olan belgeleri bulmak ve içinde yeni belgelerin açılacağı biçimi belirlemek içerir.

`CDocTemplate` belgeler ve çerçeveler için UI bağlamasını yönetir.

`CDocTemplate` adlandırılmamış belge sayısının sayısını tutar.

## <a name="cdocument"></a>CDocument

, Bir öğesine `CDocument` aittir `CDocTemplate` .

Belgeler, şu anda `CView` belgeyi (a) görüntüleyen açık görünümlerin (öğesinden türetilmiş) bir listesini vardır `CPtrList` .

Belgeler görünümleri oluşturmaz/yok eder, ancak oluşturulduktan sonra birbirlerine eklenir. Bir belge kapatıldığında (yani, dosya/kapatma aracılığıyla), tüm eklenmiş görünümler kapatılır. Belgedeki son görünüm kapatıldığında (yani, pencere/kapalı) belge kapatılacak.

`CDocument::AddView`, `RemoveView` Arabirim görünüm listesini korumak için kullanılır. `CDocument` , `CView` geri imlecini ayarlayabilmemiz için bir arkadaşınız `CView::m_pDocument` .

## <a name="cframewnd"></a>CFrameWnd

Bir `CFrameWnd` (çerçeve olarak da bilinir) MFC 1,0 ' de aynı rolü çalar, ancak artık `CFrameWnd` sınıf, yeni bir sınıf türetmeden birçok durumda kullanılmak üzere tasarlanmıştır. Türetilmiş sınıflar `CMDIFrameWnd` ve `CMDIChildWnd` çok sayıda standart komut zaten uygulanmış olacak şekilde de geliştirilmiştir.

`CFrameWnd`Çerçevenin istemci alanında Windows oluşturmaktan sorumludur. Normalde, çerçevenin istemci alanını dolduran bir ana pencere vardır.

MDI-Frame bir pencere için, istemci alanı, tüm MDI-Child çerçeve pencerelerinin üst öğesini sırasıyla MDıCLıENT denetimiyle doldurulur. SDI-Frame bir pencere veya MDI-Child çerçeve penceresinde, istemci alanı genellikle `CView` türetilmiş bir pencere nesnesi ile doldurulur. Bu durumda `CSplitterWnd` , görünümün istemci alanı `CSplitterWnd` pencere nesnesiyle doldurulmuştur ve `CView` türetilmiş pencere nesneleri (bölünmüş bölme başına bir tane), öğesinin alt pencereleri olarak oluşturulur `CSplitterWnd` .

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya göre teknik notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye göre teknik notlar](../mfc/technical-notes-by-category.md)
