---
title: Tek Bir Belgeye Birden Çok Görünüm Ekleme
ms.date: 11/04/2016
helpviewer_keywords:
- multiple views [MFC], SDI applications
- documents [MFC], multiple views
- single document interface (SDI), adding views
- views [MFC], SDI applications
ms.assetid: 86d0c134-01d5-429c-b672-36cfb956dc01
ms.openlocfilehash: 83bb7e54567319a7af4bd3d8a6bf02256fef68fb
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84623349"
---
# <a name="adding-multiple-views-to-a-single-document"></a>Tek Bir Belgeye Birden Çok Görünüm Ekleme

Microsoft Foundation Class (MFC) kitaplığı ile oluşturulan tek belgeli arabirim (SDI) uygulamasında her belge türü tek bir görünüm türüyle ilişkilendirilir. Bazı durumlarda, belgenin geçerli görünümünü yeni bir görünümle değiştirme özelliği de istenebilir.

> [!TIP]
> Tek bir belge için birden çok görünüm uygulamayla ilgili ek yordamlar için bkz. [CDocument:: AddView](reference/cdocument-class.md#addview) ve [Collect](../overview/visual-cpp-samples.md) MFC örneği.

Bu işlevi, yeni `CView` türetilmiş bir sınıf ekleyerek ve görünümleri bir mevcut MFC uygulamasına dinamik olarak değiştirmek için ek kod ekleyerek uygulayabilirsiniz.

Adımlar şu şekildedir:

- [Mevcut uygulama sınıfını değiştirme](#vcconmodifyexistingapplicationa1)

- [Yeni görünüm sınıfını oluşturma ve değiştirme](#vcconnewviewclassa2)

- [Yeni görünüm oluştur ve Ekle](#vcconattachnewviewa3)

- [Anahtarlama Işlevini uygulama](#vcconswitchingfunctiona4)

- [Görünümü değiştirmek için destek ekleme](#vcconswitchingtheviewa5)

Bu konunun geri kalanında aşağıdakiler varsayılmaktadır:

- `CWinApp`Türetilmiş nesnenin adı `CMyWinApp` , ve `CMyWinApp` MyWinApp içinde bildirilmiştir ve tanımlanmıştır *. H* ve *MyWinApp. CPP*.

- `CNewView``CView`, yeni türetilmiş nesnenin adıdır ve `CNewView` NewView içinde bildirilmiştir ve tanımlanır *. H* ve *NewView. CPP*.

## <a name="modify-the-existing-application-class"></a><a name="vcconmodifyexistingapplicationa1"></a>Mevcut uygulama sınıfını değiştirme

Uygulamanın görünümler arasında geçmesi için, görünümleri depolamak için üye değişkenleri ve bunları değiştirmek için bir yöntem ekleyerek uygulama sınıfını değiştirmeniz gerekir.

Aşağıdaki kodu `CMyWinApp` *MyWinApp içindeki bildirimine ekleyin. H*:

[!code-cpp[NVC_MFCDocViewSDI#1](codesnippet/cpp/adding-multiple-views-to-a-single-document_1.h)]

Yeni üye değişkenleri `m_pOldView` ve `m_pNewView` , geçerli görünümü ve yeni oluşturulan bir görünüm üzerine gelin. Yeni Yöntem ( `SwitchView` ), Kullanıcı tarafından istendiğinde görünümleri geçirir. Yönteminin gövdesi, bu konunun daha sonra [anahtarlama Işlevini uygulama](#vcconswitchingfunctiona4)bölümünde ele alınmıştır.

Uygulama sınıfına yapılan son değişiklik, anahtarlama işlevinde kullanılan bir Windows iletisini (**WM_INITIALUPDATE**) tanımlayan yeni bir üst bilgi dosyası da dahil olmasını gerektirir.

MyWinApp 'in içerme bölümüne aşağıdaki satırı ekleyin *. CPP*:

[!code-cpp[NVC_MFCDocViewSDI#2](codesnippet/cpp/adding-multiple-views-to-a-single-document_2.cpp)]

Değişikliklerinizi kaydedin ve bir sonraki adımla devam edin.

## <a name="create-and-modify-the-new-view-class"></a><a name="vcconnewviewclassa2"></a>Yeni görünüm sınıfını oluşturma ve değiştirme

Yeni görünüm sınıfının oluşturulması, Sınıf Görünümü tarafından kullanılabilen **Yeni sınıf** komutu kullanılarak kolayca yapılır. Bu sınıf için tek gereksinim, öğesinden türetilmiş olur `CView` . Bu yeni sınıfı uygulamaya ekleyin. Projeye yeni bir sınıf ekleme hakkında ayrıntılı bilgi için bkz. [sınıf ekleme](../ide/adding-a-class-visual-cpp.md).

Sınıfı projeye ekledikten sonra bazı görünüm sınıfı üyelerinin erişilebilirliğini değiştirmeniz gerekir.

*NewView 'ı değiştirin. *Erişim belirticisini, Oluşturucu ve yıkıcısı için **korunan** olarak **ortak** olarak değiştirerek H. Bu, sınıfın dinamik olarak oluşturulmasını ve yok edilmesinin yanı sıra, görünür olmadan önce görünüm görünümünü değiştirmesini sağlar.

Değişikliklerinizi kaydedin ve bir sonraki adımla devam edin.

## <a name="create-and-attach-the-new-view"></a><a name="vcconattachnewviewa3"></a>Yeni görünüm oluştur ve Ekle

Yeni görünümü oluşturup eklemek için, `InitInstance` uygulama sınıfınızın işlevini değiştirmeniz gerekir. Değişiklik, yeni bir görünüm nesnesi oluşturan yeni kod ekler ve ardından hem hem de `m_pOldView` `m_pNewView` varolan iki görünüm nesnesiyle birlikte başlatılır.

Yeni görünüm işlev içinde oluşturulduğundan `InitInstance` , hem yeni hem de mevcut görünümler uygulamanın kullanım ömrü boyunca kalır. Ancak, uygulama yeni görünümü dinamik olarak kolayca oluşturabilir.

Çağrısından sonra bu kodu Ekle `ProcessShellCommand` :

[!code-cpp[NVC_MFCDocViewSDI#3](codesnippet/cpp/adding-multiple-views-to-a-single-document_3.cpp)]

Değişikliklerinizi kaydedin ve bir sonraki adımla devam edin.

## <a name="implement-the-switching-function"></a><a name="vcconswitchingfunctiona4"></a>Anahtarlama Işlevini uygulama

Önceki adımda yeni bir görünüm nesnesi oluşturan ve başlatılan kodu eklediniz. Son ana parça, değiştirme yöntemini uygulamaktır `SwitchView` .

Uygulama sınıfınızın (MyWinApp) uygulama dosyasının sonunda *. CPP*), aşağıdaki yöntem tanımını ekleyin:

[!code-cpp[NVC_MFCDocViewSDI#4](codesnippet/cpp/adding-multiple-views-to-a-single-document_4.cpp)]

Değişikliklerinizi kaydedin ve bir sonraki adımla devam edin.

## <a name="add-support-for-switching-the-view"></a><a name="vcconswitchingtheviewa5"></a>Görünümü değiştirmek için destek ekleme

Son adım, uygulamanın görünümler arasında geçmesi gerektiğinde yöntemini çağıran kodun eklenmesini içerir `SwitchView` . Bu işlem birkaç yolla yapılabilir: Kullanıcı için yeni bir menü öğesi ekleyerek, belirli koşullar karşılandığında görünümleri dahili olarak seçme veya değiştirme.

Yeni menü öğeleri ve komut işleyici işlevleri ekleme hakkında daha fazla bilgi için bkz. [komut ve denetim bildirimleri Için işleyiciler](handlers-for-commands-and-control-notifications.md).

## <a name="see-also"></a>Ayrıca bkz.

[Belge/görünüm mimarisi](document-view-architecture.md)
