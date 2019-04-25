---
title: 'TN030: Yazdırmayı ve Baskı Önizlemeyi özelleştirme'
ms.date: 06/28/2018
f1_keywords:
- vc.print
helpviewer_keywords:
- TN030
- customizing printing and print preview
- printing [MFC], views
- printing views [MFC]
- print preview [MFC], customizing
ms.assetid: 32744697-c91c-41b6-9a12-b8ec01e0d438
ms.openlocfilehash: 09938c5cec2812998d5e76e15154754ad3ac3e0b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62305690"
---
# <a name="tn030-customizing-printing-and-print-preview"></a>TN030: Yazdırmayı ve Baskı Önizlemeyi özelleştirme

> [!NOTE]
> Aşağıdaki Teknik Not çevrimiçi belgelere ilk eklenmiştir beri güncelleştirilmemiş. Eski veya yanlış sonuç olarak, bazı yordamlar ve konular olabilir. En son bilgiler için bu konuyu çevrimiçi belge dizininde arama önerilir.

Bu Not, yazdırmayı ve Baskı Önizlemeyi özelleştirme işlemi açıklanır ve kullanılan geri çağırma rutinleri amaçları açıklanır `CView` geri çağırma yordamları ve üye işlevleri ve `CPreviewView`.

## <a name="the-problem"></a>Sorun

MFC çoğu yazdırma için eksiksiz bir çözüm sağlar ve baskı önizlemeyi gerekiyor. Çoğu durumda, yazdırma ve Önizleme görünümü için çok az ek kod gereklidir. Ancak, önemli miktarda çaba Geliştirici tarafında gerektiren yazdırma iyileştirmek için yolu vardır ve bazı uygulamalar belirli kullanıcı arabirimi öğeleri için Yazdırma Önizleme modundan eklemeniz gerekir.

## <a name="efficient-printing"></a>Verimli yazdırma

Bir MFC uygulaması standart yöntemlerini kullanarak yazdırdığında Windows grafik cihaz arabirimi (GDI) çıkış bir bellek içi meta dosyası alt çağrısına yönlendirir. Zaman `EndPage` olan çağrılır, Windows Meta dosyası için bir kez bir sayfa yazdırmak için yazıcı gerektiren her fiziksel bant yürütülür. Bu işleme sırasında GDI sık durdurma devam edip etmediğini belirlemek için yordamı sorgular. Genellikle kullanıcının bir yazdırma iletişim kutusunu kullanarak yazdırma işi iptal etmek için işlenecek iletilerin iptal yordam sağlar.

Ne yazık ki bu yazdırma işlemi yavaşlatabilir. Uygulamanızdaki yazdırma standart tekniği kullanarak gerçekleştirilebilir çok hızlı olması gerekiyorsa, el ile bant uygulamalıdır.

## <a name="print-banding"></a>Bant yazdırma

El ile bant için yeniden yazdırma döngü uygulamanız gereken şekilde `OnPrint` (bir kez başına bant) ile ilgili sayfa başına birden çok kez çağrılır. Yazdırma döngü uygulanan `OnFilePrint` viewprnt.cpp işlevi. İçinde `CView`-türetilmiş sınıf, böylelikle yazdırma komutunu işlemek için ileti eşleme girişi yazdırma işlevinizi çağıran bu işlev aşırı yükleme. Kopyalama `OnFilePrint` yordamı ve değişiklik banding uygulamak için yazdırma döngü. Muhtemelen de çizim yazdırılan sayfanın bölümüne göre iyileştirebilirsiniz. böylece, yazdırma işlevlerinizi Şerit dikdörtgen geçirmek istediğiniz.

İkinci olarak, sık çağırmalısınız `QueryAbort` bant çizim sırasında. Aksi takdirde iptal yordamı yok adlı ve kullanıcı yazdırmayı iptal etmek mümkün olmayacaktır.

## <a name="print-preview-electronic-paper-with-user-interface"></a>Baskı Önizleme: Kullanıcı arabirimi ile elektronik İnceleme

Baskı Önizleme, esas olarak, bir yazıcı öykünmesini ekranını açmak çalışır. Varsayılan olarak, ana pencerenin istemci alanının penceresi içinde tam olarak bir veya iki sayfa görüntülemek için kullanılır. Kullanıcı bir alanı daha ayrıntılı olarak görmek için sayfayı yakınlaştırır mümkün değil. Ek destek içeren kullanıcı bile önizleme modunda belgeyi düzenlemek için izin verilmiyor olabilir.

## <a name="customizing-print-preview"></a>Baskı Önizlemeyi özelleştirme

Bu not yalnızca baskı önizlemeyi değiştirme yönlerinden biri ile ilgilidir: Önizleme modu için kullanıcı Arabirimi ekleme. Diğer değişiklikler mümkündür, ancak bu tür değişiklikler bu tartışma kapsamı dışında.

## <a name="to-add-ui-to-the-preview-mode"></a>Önizleme modunu için kullanıcı Arabirimi eklemek için

1. Bir görünümü sınıfından türetilir `CPreviewView`.

2. İstediğiniz kullanıcı Arabirimi yönleri için komut işleyicileri ekleyin.

3. Görüntülenecek görsel özellikleri ekliyorsanız, geçersiz kılma `OnDraw` ve sonra arama, çizim gerçekleştirmek `CPreviewView::OnDraw`.

## <a name="onfileprintpreview"></a>OnFilePrintPreview

Baskı Önizleme için komut işleyicisi budur. Kendi varsayılan uygulamasıdır:

```cpp
void CView::OnFilePrintPreview()
{
    // In derived classes, implement special window handling here
    // Be sure to Unhook Frame Window close if hooked.

    // must not create this on the frame. Must outlive this function
    CPrintPreviewState* pState = new CPrintPreviewState;

    if (!DoPrintPreview(AFX_IDD_PREVIEW_TOOLBAR, this,
        RUNTIME_CLASS(CPreviewView), pState))
    {
        // In derived classes, reverse special window handling
        // here for Preview failure case

        TRACE0("Error: DoPrintPreview failed");
        AfxMessageBox(AFX_IDP_COMMAND_FAILURE);
        delete pState;  // preview failed to initialize, delete State now
    }
}
```

`DoPrintPreview` uygulamanın ana bölmede gizler. Denetim çubukları, durum çubuğu gibi tutulabilir içinde pState belirterek ->*dwStates* üyesi (Bu, bir bit maskesi ve BITS bağımsız denetim çubukları AFX_CONTROLBAR_MASK (AFX_IDW_MYBAR) tarafından tanımlanan için). Pencere pState ->*nIDMainPane* otomatik olarak gizli ve reshown penceredir. `DoPrintPreview` ardından bir düğme çubuğu için standart Önizleme kullanıcı Arabirimi oluşturacaksınız. Özel pencere işleme gerekirse, önce yapılmalıdır diğer windows, göstermek veya gizlemek için gibi `DoPrintPreview` çağrılır.

Baskı Önizleme sona erdiğinde, varsayılan olarak, Denetim çubuklarını özgün durumlarını ve ana bölmede görünür için döndürür. Özel işleme gerekirse, bu geçersiz kılma yapılmalıdır `EndPrintPreview`. Varsa `DoPrintPreview` başarısız oldu, özel işlem de sağlar.

DoPrintPreview çağrılır:

- Önizleme araç çubuğu iletişim şablonu kaynak kimliği.

- Yazdırma için yazdırma önizleme gerçekleştirmek için bir görünüm için bir işaretçi.

- Çalışma zamanı sınıf Önizleme Görünüm sınıfı. Bu, içinde DoPrintPreview dinamik olarak oluşturulur.

- CPrintPreviewState işaretçisi. Not CPrintPreviewState yapısını (veya uygulamanın daha fazla durum korunur gerekiyorsa türetilen yapısı) gerektiğini *değil* karesinde oluşturulabilir. Kalıcı olmayan DoPrintPreview ve EndPrintPreview çağrılana kadar bu yapı varlığını sürdürmesini gerekir.

  > [!NOTE]
  > Yazdırma desteği için ayrı bir görünüm veya Görünüm sınıfı gerekiyorsa, bu nesneye bir işaretçi ikinci parametre olarak geçirilmelidir.

## <a name="endprintpreview"></a>EndPrintPreview

Baskı Önizleme modunu sonlandırmak için çağrılır. Genellikle, baskı önizlemede son görüntülenen belgedeki sayfayı taşımak için tercih edilir. `EndPrintPreview` Bunu yapmak için uygulamanın şansınızdır. PInfo ->*m_nCurPage* üyesi olan en son (en soldaki iki sayfa görüntülenirse) görüntülenen sayfa ve işaretçi, sayfada kullanıcı ilgileniyor nerede dair bir ipucu verir. Uygulamanın görünümü yapısını framework bilinmeyen olduğundan, seçilen noktaya gitme kod sağlamanız gerekir.

Çoğu eylemleri çağırmadan önce gerçekleştirmeniz gereken `CView::EndPrintPreview`. Bu çağrı etkilerini tersine çevirir `DoPrintPreview` ve pView, pDC ve pInfo siler.

```cpp
// Any further cleanup should be done here.
CView::EndPrintPreview(pDC, pInfo, point, pView);
```

## <a name="cwinapponfileprintsetup"></a>CWinApp::OnFilePrintSetup

Bu, Yazdırma Kurulumu menü öğesi için eşlenmelidir. Çoğu durumda, uygulama geçersiz kılmak gerekli değildir.

## <a name="page-nomenclature"></a>Sayfa terminolojisi

Başka bir sorun ve sayfa numaralandırma sırasını olmasıdır. Basit bir sözcük işlemcisi türü uygulamalar için bu basit bir sorundur. Baskı Önizleme sistemlerinin çoğu, her sayfada belgedeki bir sayfasına karşılık gelen varsayılır.

Genelleştirilmiş bir çözüm sağlamak çalışırken dikkat etmeniz gereken birkaç nokta vardır. CAD sistem düşünün. Kullanıcının birden fazla E-boyutunu sayfaları kapsayan Çizim yok. Bir E-boyutu (veya daha küçük, ölçeği) çizici olduğu gibi basit bir durumda olurdu sayfa numaralandırma. Ancak, sayfa başına 16 bir boyut sayfa yazdırma bir lazer yazıcı üzerinde ne baskı önizlemeyi "page" dikkate almaz

Giriş paragrafı durumları gibi yazdırma önizleme yazıcı gibi davranır. Bu nedenle, kullanıcının ne seçili belirli yazıcı dışında gelecektir görürsünüz. Bu görünüm görüntüyü her sayfada yazdırılır belirlemek için en fazla olur.

Sayfa açıklaması dizesinde `CPrintInfo` yapı sayfa başına bir sayı olarak temsil edilebilir değilse, kullanıcıya sayfa numarası görüntüleme bir yol sağlar ("1. sayfası" olduğu gibi veya "sayfaları 1-2"). Bu dize, varsayılan uygulaması tarafından kullanılan `CPreviewView::OnDisplayPageNumber`. Farklı bir ekrana gerekirse, bir örneğin, "Sayfa1, bölümleri A, B" sağlamak için bu sanal işlevi geçersiz kılabilir.

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya Göre Teknik Notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)
