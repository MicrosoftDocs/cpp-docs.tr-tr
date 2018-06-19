---
title: 'TN030: Yazdırmayı ve Baskı Önizlemeyi özelleştirme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.print
dev_langs:
- C++
helpviewer_keywords:
- TN030
- customizing printing and print preview
- printing [MFC], views
- printing views [MFC]
- print preview [MFC], customizing
ms.assetid: 32744697-c91c-41b6-9a12-b8ec01e0d438
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 342edd56ee279de0b854c8e8ceb177b797a03f3b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33384617"
---
# <a name="tn030-customizing-printing-and-print-preview"></a>TN030: Yazdırmayı ve Baskı Önizlemeyi Özelleştirme
> [!NOTE]
>  İlk çevrimiçi belgelerinde eklenmiştir beri aşağıdaki Teknik Not güncelleştirilmemiş. Sonuç olarak, bazı yordamlar ve konuları güncel veya yanlış olması olabilir. En son bilgiler için çevrimiçi belgeleri dizindeki ilgi konuyu aramak önerilir.  
  
 Bu Not yazdırmayı ve Baskı Önizlemeyi özelleştirme işlemi açıklanır ve kullanılan geri çağırma yordamları amaçları açıklar `CView` ve geri çağırma yordamları ve de üye işlevlerini **CPreviewView**.  
  
## <a name="the-problem"></a>Sorun  
 MFC çoğu yazdırmak için eksiksiz bir çözüm sağlar ve Baskı Önizleme gerekiyor. Çoğu durumda, yazdırma ve Önizleme görünümü için çok az ek kod gereklidir. Ancak, geliştirici bölümüne önemli çaba gerektiren yazdırma en iyi duruma getirme yolu vardır ve Baskı Önizleme modunu belirli bir kullanıcı arabirimi öğeleri eklemek bazı uygulamaları gerekir.  
  
## <a name="efficient-printing"></a>Verimli yazdırma  
 MFC uygulaması standart yöntemlerini kullanarak yazdırdığında, Windows bir bellek içi meta dosyası tüm grafik cihaz arabirimi (GDI) çıkış çağrıları yönlendirir. Zaman `EndPage` olduğu adlı Windows Meta dosyası bir kez bir sayfa yazdırmak için yazıcı gerektirir her fiziksel bant için oynatılır. Bu işleme sırasında GDI sık devam edip etmediğini belirlemek için Abort yordamı sorgular. Genellikle kullanıcı yazdırma iletişim kutusunu kullanarak yazdırma işi iptal etmek için işlenmeye iletileri iptal yordam sağlar.  
  
 Ne yazık ki, bu yazdırma işlemini yavaşlatabilir. Yazdırma, uygulamanızda standart teknik kullanılarak sağlanabilir daha hızlı olması gerekiyorsa, el ile bant uygulamalıdır.  
  
## <a name="print-banding"></a>Bant yazdırma  
 El ile bant için re yazdırma döngü uygulamanız gereken şekilde `OnPrint` sayfa (kez başına bant) başına birden çok kez çağrılır. Yazdırma döngü uygulanan **OnFilePrint** viewprnt.cpp işlevinde. İçinde `CView`-türetilmiş sınıf, böylece yazdırma işlevinizin yazdırma komutunu işlemek için ileti eşlemesi girişi çağırır bu işlev aşırı yükleme. Kopya **OnFilePrint** yordamı ve değişiklik bant uygulamak için yazdırma döngü. Muhtemelen da yazdırılmasını sayfasının bölümüne dayalı çizim en iyi duruma getirebilirsiniz böylece Şerit dikdörtgen yazdırma işlevlerinizi geçirmek istediğiniz.  
  
 İkinci olarak, sık çağırmalısınız `QueryAbort` bant çizim sırasında. Aksi takdirde iptal yordamı yok adlı ve kullanıcı yazdırma işi iptal etmek erişemez.  
  
## <a name="print-preview-electronic-paper-with-user-interface"></a>Baskı Önizleme: Elektronik kağıt kullanıcı arabirimi  
 Baskı Önizleme, esas olarak, görüntü bir öykünme yazıcının içine dönüştürmeye çalışır. Varsayılan olarak, istemci alanını ana penceresinin penceresi içinde tam olarak bir veya iki sayfa görüntülemek için kullanılır. Kullanıcı daha ayrıntılı olarak görmek için page alanı yakınlaştırmak mümkün değil. Ek destek ile kullanıcı bile önizleme modunda belgeyi düzenlemesine izin.  
  
## <a name="customizing-print-preview"></a>Baskı Önizlemeyi özelleştirme  
 Bu not yalnızca Baskı Önizleme değiştirme bir boyut ile ilgilidir: önizleme modu için kullanıcı Arabirimi ekleme. Diğer tüm değişiklikleri olası, ancak bu değişiklikleri bu tartışma kapsam dışındadır.  
  
## <a name="to-add-ui-to-the-preview-mode"></a>UI Önizleme moduna eklemek için  
  
1.  Bir görünüm sınıfından türetilen **CPreviewView**.  
  
2.  İstediğiniz UI yönleri için komut işleyicileri ekleyin.  
  
3.  Görüntülenecek visual yönlerini ekliyorsanız, geçersiz kılma `OnDraw` ve çağırdıktan sonra çizim gerçekleştirmek **CPreviewView::OnDraw.**  
  
## <a name="onfileprintpreview"></a>OnFilePrintPreview  
 Baskı Önizleme için komut işleyici budur. Kendi varsayılan uygulamadır:  
  
```  
void CView::OnFilePrintPreview()  
{ *// In derived classes,
    implement special window handling here *// Be sure to Unhook Frame Window close if hooked.  
 *// must not create this on the frame. Must outlive this function  
    CPrintPreviewState* pState = new CPrintPreviewState;  
 
    if (!DoPrintPreview(AFX_IDD_PREVIEW_TOOLBAR,
    this,  
    RUNTIME_CLASS(CPreviewView),
    pState))  
 { *// In derived classes,
    reverse special window handling *// here for Preview failure case  
 
    TRACE0("Error: DoPrintPreview failed");

    AfxMessageBox(AFX_IDP_COMMAND_FAILURE);

 delete pState;      // preview failed to initialize, *// delete State now  
 }  
}  
```  
  
 **DoPrintPreview** uygulamasının ana bölmesi gizlenir. Denetim çubukları durum çubuğu gibi saklanabilir pState belirterek ->**dwStates** üyesi (Bu bir bit maskesi ve tek tek denetim çubukları BITS tarafından tanımlanan **AFX_CONTROLBAR_MASK**(AFX_IDW_MYBAR)). Pencere pState ->**nIDMainPane** otomatik olarak reshown ve gizlenecek bir penceredir. **DoPrintPreview** düğme çubuğu için standart Önizleme UI ardından oluşturur. Özel pencere işleme gerekiyorsa, önce yapılmalıdır diğer windows, göstermek veya gizlemek gibi **DoPrintPreview** olarak adlandırılır.  
  
 Baskı Önizleme sona erdiğinde, varsayılan olarak, bu denetim çubukları özgün durumlarını ve görünür ana bölmesine döndürür. Özel işleme gerekiyorsa, bu geçersiz kılma içinde yapılmalıdır **EndPrintPreview.** Varsa **DoPrintPreview** başarısız oldu, özel işleme de sağlar.  
  
 DoPrintPreview çağrılır:  
  
-   Önizleme araç iletişim şablonu kaynak kimliği.  
  
-   Baskı Önizleme için yazdırma gerçekleştirmek için Görünüm için bir işaretçi.  
  
-   Önizleme görünümü sınıfının çalışma zamanı sınıf. Bu, DoPrintPreview içinde dinamik olarak oluşturulur.  
  
-   CPrintPreviewState işaretçi. CPrintPreviewState yapısı (veya uygulama korunur daha fazla durum gerekiyorsa türetilmiş yapısı) gerektiğini Not *değil* çerçevesi oluşturulabilir. DoPrintPreview kalıcı olmayan ve EndPrintPreview çağrılıncaya kadar bu yapı varlığını sürdürmesini gerekir.  
  
    > [!NOTE]
    >  Ayrı görünüm veya Görünüm sınıfı yazdırma desteği için gerekiyorsa, bu nesne için bir işaretçi ikinci parametre olarak geçirilmesi gerekir.  
  
## <a name="endprintpreview"></a>EndPrintPreview  
 Bu, Baskı Önizleme modunu sonlandırmak için çağrılır. Genellikle, en son Baskı Önizlemede görüntülenen belge sayfası taşımak için tercih edilir. **EndPrintPreview** Bunu yapmak için uygulamanın şansınızdır. PInfo ->`m_nCurPage` üyesidir son (en soldaki iki sayfa görüntüleniyorsa) görüntülenen sayfa ve işaretçisi sayfasında kullanıcı burada ilgileniyor konusunda ipucu. Uygulamanın görünümü yapısını framework bilinmeyen olduğundan, seçilen noktasına taşımak için kodu sağlamanız gerekir.  
  
 Çağırmadan önce çoğu Eylemler gerçekleştirmesi gereken **CView::EndPrintPreview**. Bu çağrı etkilerini tersine çevirir **DoPrintPreview** ve pView, pDC ve pInfo siler.  
  
```  
// Any further cleanup should be done here.  
CView::EndPrintPreview(pDC,
    pInfo,
    point,
    pView);
```  
  
## <a name="cwinapponfileprintsetup"></a>CWinApp::OnFilePrintSetup  
 Bu sayfa yapısı menü öğesi için eşlenmelidir. Çoğu durumda, uygulama geçersiz kılmak gerekli değildir.  
  
## <a name="page-nomenclature"></a>Sayfa terminolojisi  
 Başka bir sorun sayfa numaralandırma ve order olmasıdır. Basit sözcük işlemci türü uygulamalar için bu basit bir sorundur. Baskı Önizleme sistemlerinin çoğu her sayfada belgede bir sayfaya karşılık gelen varsayalım.  
  
 Genelleştirilmiş bir çözüm sağlamak çalışırken dikkate alınması gereken birkaç nokta vardır. CAD sistem düşünün. Kullanıcının birden fazla E-boyutunu sayfaları kapsayan bir çizim vardır. Bir E-boyutu (veya daha küçük, ölçeği) çizici, olduğu gibi basit bir durumda olacaktır sayfa numaralandırma. Ancak başına, 16 A boyutu sayfa yazdırma bir lazer yazıcı üzerinde ne Baskı Önizleme "Sayfa" dikkate almaz  
  
 Giriş paragrafı durumları gibi baskı önizleme yazıcı gibi davranır. Bu nedenle, kullanıcının ne seçili belirli yazıcı dışında gelecektir görürsünüz. Hangi görüntü her sayfada yazdırılır belirlemek için görünümünün kadar olur.  
  
 Sayfa açıklama dizesi `CPrintInfo` yapı sayfa başına bir sayı olarak gösterilebilir, sayfa numarası kullanıcıya görüntüleme yolu sağlar (olduğu gibi "Sayfa 1" veya "sayfaları 1-2"). Bu dize varsayılan uygulaması tarafından kullanılan **CPreviewView::OnDisplayPageNumber**. Farklı görüntüleme gerekiyorsa, biri, örneğin, "Sheet1, bölümler A, B" sağlamak için bu sanal işlevi geçersiz kılabilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sayıya göre teknik notlar](../mfc/technical-notes-by-number.md)   
 [Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)

