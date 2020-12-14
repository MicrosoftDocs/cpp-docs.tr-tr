---
description: 'Hakkında daha fazla bilgi edinin: TN030: yazdırma ve Baskı Önizlemeyi özelleştirme'
title: 'TN030: Yazdırmayı ve Baskı Önizlemeyi Özelleştirme'
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
ms.openlocfilehash: 6fc0571b908f85b24b8a0752a00842077d537dce
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97215618"
---
# <a name="tn030-customizing-printing-and-print-preview"></a>TN030: Yazdırmayı ve Baskı Önizlemeyi Özelleştirme

> [!NOTE]
> Aşağıdaki teknik Not, çevrimiçi belgelere ilk eklenmesinden beri güncelleştirilmemiş. Sonuç olarak, bazı yordamlar ve konular güncel olmayabilir veya yanlış olabilir. En son bilgiler için çevrimiçi belge dizininde ilgilendiğiniz konuyu aramanız önerilir.

Bu notta, yazdırma ve Baskı Önizlemeyi özelleştirme ve içinde kullanılan geri çağırma yordamlarının ve `CView` geri çağırma yordamlarının ve üye işlevlerinin amaçları açıklanmaktadır `CPreviewView` .

## <a name="the-problem"></a>Sorun

MFC, en çok yazdırma ve baskı önizleme gereksinimlerine yönelik bir çözüm sunar. Çoğu durumda, bir görünümün yazdırılması ve önizlenmesi için biraz daha fazla kod gereklidir. Ancak, geliştiricinin bölümünde önemli bir çaba gerektiren yazdırmayı en iyi hale getirmeye yönelik yollar vardır ve bazı uygulamaların Baskı Önizleme moduna belirli kullanıcı arabirimi öğelerini eklemesi gerekir.

## <a name="efficient-printing"></a>Verimli Yazdırma

Bir MFC uygulaması standart yöntemleri kullanarak yazdırıldığında, Windows tüm grafik cihaz arabirimi (GDI) çıkış çağrılarını bellek içi meta dosyasına yönlendirir. `EndPage`Çağrıldığında, yazıcı bir sayfa yazdırmak için gereken her fiziksel bant için, Windows meta dosyasını bir kez yürütür. Bu işleme sırasında GDI, devam edip edemediğine yönelik olarak genellikle Abort yordamını sorgular. Genellikle, iptal yordamı, kullanıcının yazdırma işini bir yazdırma iletişim kutusu kullanarak durdurabilmesi için iletilerin işlenmesine izin verir.

Ne yazık ki bu, yazdırma işlemini yavaşlatabilir. Uygulamanızdaki yazdırmanın standart tekniği kullanarak elde edilebileceğinden daha hızlı olması gerekiyorsa, el ile bant uygulamanız gerekir.

## <a name="print-banding"></a>Bantyı Yazdır

El ile bantlamak için, `OnPrint` sayfa başına birden çok kez çağrılan Yazdırma döngüsünü yeniden uygulamanız gerekir (her bant için bir kez). Print döngüsü `OnFilePrint` viewprnt. cpp işlevine uygulanır. `CView`Türetilmiş sınıfınıza, Print komutunu işlemeye yönelik ileti eşleme girişi Print işlevinizi çağırabilmeniz için bu işlevi aşırı yükleyebilirsiniz. Yordamı kopyalayın `OnFilePrint` ve yazdırma döngüsünü, bantyı uygulayacak şekilde değiştirin. Ayrıca, yazdırılan sayfanın bölümüne göre çizimi iyileştirebilmeniz için, büyük olasılıkla yazdırma işlevlerinizi bant içine geçirmek isteyeceksiniz.

İkinci olarak, bandı çizerken sıklıkla çağrı yapmanız gerekir `QueryAbort` . Aksi takdirde, Iptal prosedürü çağrılmaz ve Kullanıcı, yazdırma işini iptal edemeyecektir.

## <a name="print-preview-electronic-paper-with-user-interface"></a>Baskı Önizleme: Kullanıcı arabirimiyle elektronik kağıt

Baskı Önizleme, temelde, görüntüyü bir yazıcı öykünmesine geçirmeye çalışır. Varsayılan olarak, ana pencerenin istemci alanı bir veya iki sayfayı pencere içinde tam olarak göstermek için kullanılır. Kullanıcı, daha ayrıntılı bir şekilde görmek için sayfanın bir alanını yakınlaştırabilir. Ek destek sayesinde, Kullanıcı, önizleme modunda belgeyi düzenlemeye da izin verebilir.

## <a name="customizing-print-preview"></a>Baskı Önizlemeyi özelleştirme

Bu durum yalnızca baskı önizlemeyi değiştirmenin bir yönü ile ilgilidir: Önizleme moduna Kullanıcı arabirimi ekleme. Diğer değişiklikler mümkündür, ancak bu değişiklikler bu tartışmanın kapsamında değildir.

## <a name="to-add-ui-to-the-preview-mode"></a>Önizleme moduna Kullanıcı arabirimi eklemek için

1. Öğesinden bir görünüm sınıfı türet `CPreviewView` .

2. İstediğiniz UI yönleri için komut işleyicileri ekleyin.

3. Görsele görsel yönleri ekliyorsanız, `OnDraw` çağırdıktan sonra Çiziminizi geçersiz kılın ve gerçekleştirin `CPreviewView::OnDraw` .

## <a name="onfileprintpreview"></a>OnFilePrintPreview

Bu, baskı önizleme için komut işleyicisidir. Varsayılan uygulama:

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

`DoPrintPreview` uygulamanın ana bölmesini gizleyecek. Durum çubuğu gibi denetim çubukları, bunları pState->*dwStates* üyesinde belirterek korunabilir (Bu bir bit maskesidir ve bireysel denetim çubuklarının bitleri AFX_CONTROLBAR_MASK (AFX_IDW_MYBAR) tarafından tanımlanır). Pencere pState->*nIDMainPane* , otomatik olarak gizli ve reshown olacak bir penceredir. `DoPrintPreview` sonra standart önizleme Kullanıcı arabirimi için bir düğme çubuğu oluşturur. Özel pencere işleme gerekiyorsa (diğer pencereleri gizleme veya gösterme gibi), çağrılmadan önce yapılması gereken `DoPrintPreview` .

Varsayılan olarak, baskı önizleme tamamlandığında, denetim çubuklarını orijinal durumlarına ve ana bölmeye görünür hale getirir. Özel işleme gerekiyorsa, bir geçersiz kılmada yapılmalıdır `EndPrintPreview` . `DoPrintPreview`Başarısız olursa, özel işlem de sağlar.

DoPrintPreview şu şekilde çağrılır:

- Önizleme araç çubuğunun iletişim şablonunun kaynak KIMLIĞI.

- Baskı Önizleme için yazdırmayı gerçekleştirecek görünüme yönelik bir işaretçi.

- Önizleme görünümü sınıfının çalışma zamanı sınıfı. Bu, DoPrintPreview 'da dinamik olarak oluşturulur.

- CPrintPreviewState işaretçisi. CPrintPreviewState yapısının (ya da uygulamanın daha fazla durum korunmuş olması durumunda türetilmiş yapının) *oluşturulmadığından* emin olun. DoPrintPreview kalıcı değildir ve EndPrintPreview çağrılana kadar bu yapının olması gerekir.

  > [!NOTE]
  > Yazdırma desteği için ayrı bir görünüm veya Görünüm sınıfı gerekliyse, bu nesneye yönelik bir işaretçi ikinci parametre olarak geçirilmelidir.

## <a name="endprintpreview"></a>EndPrintPreview

Bu, Baskı Önizleme modunu sonlandırmak için çağırılır. Son olarak, baskı önizlemede son görüntülenen belgede bulunan sayfaya gitmek tercih edilir. `EndPrintPreview` uygulamanın bunu yapma şansı vardır. PInfo->*m_nCurPage* üyesi, son görüntülenen sayfasıdır (iki sayfa görüntüleniyorsa en solda) ve işaretçi, kullanıcının ilgilendiğiniz sayfada olduğu gibi bir ipucu olur. Uygulama görünümünün yapısı Framework 'e bilinmediği için, seçili noktaya geçmek üzere kodu sağlamalısınız.

Çağrılmadan önce çoğu eylemi gerçekleştirmeniz gerekir `CView::EndPrintPreview` . Bu çağrı, etkilerini tersine çevirir `DoPrintPreview` ve pView, PDC ve pInfo 'yi siler.

```cpp
// Any further cleanup should be done here.
CView::EndPrintPreview(pDC, pInfo, point, pView);
```

## <a name="cwinapponfileprintsetup"></a>CWinApp:: OnFilePrintSetup

Bu, yazdırma ayarı menü öğesi için eşlenmelidir. Çoğu durumda, uygulamanın geçersiz kılınması gerekli değildir.

## <a name="page-nomenclature"></a>Sayfa terminolojisi

Diğer bir sorun da sayfa numaralandırmasında ve sıralamasında bulunur. Basit sözcük işlemci türü uygulamalar için bu basit bir sorundur. Çoğu Baskı Önizleme sistemi, yazdırılan her sayfanın belgedeki bir sayfaya karşılık geldiğini varsayar.

Genelleştirilmiş bir çözüm sağlamaya çalışırken göz önünde bulundurmanız gereken birkaç nokta vardır. Bir CAD sistemi düşünün. Kullanıcının birkaç E-boyut sayfasını içeren bir çizimi vardır. Bir E-Boyut (veya küçük ölçekli) çizicide, sayfa numaralandırması basit durumda olacaktır. Ancak lazer bir yazıcıda, sayfa başına 16 A boyutunda sayfa yazdırma, baskı önizlemede "sayfa" dikkate alınması gerekenler

Tanıtım paragrafı durumları olarak baskı önizleme bir yazıcı gibi davranır. Bu nedenle, Kullanıcı seçili olan yazıcıda nelerin olacağını görür. Her sayfada hangi görüntünün yazdırıldığını belirlemek için görünüme sahiptir.

Yapıdaki sayfa açıklaması dizesi, sayfa `CPrintInfo` numarasını ("sayfa 1" veya "sayfalar 1-2" içinde olduğu gibi) göstermek için Kullanıcı için bir yol sağlar. Bu dize varsayılan uygulamasının tarafından kullanılır `CPreviewView::OnDisplayPageNumber` . Farklı bir görüntü gerekiyorsa, birisi bu sanal işlevi geçersiz kılabilir, örneğin "Sheet1, Bölüm A, B".

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya göre teknik notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye göre teknik notlar](../mfc/technical-notes-by-category.md)
