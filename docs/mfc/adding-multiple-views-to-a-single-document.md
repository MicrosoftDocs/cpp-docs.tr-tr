---
title: Tek Bir Belgeye Birden Çok Görünüm Ekleme
ms.date: 11/04/2016
helpviewer_keywords:
- multiple views [MFC], SDI applications
- documents [MFC], multiple views
- single document interface (SDI), adding views
- views [MFC], SDI applications
ms.assetid: 86d0c134-01d5-429c-b672-36cfb956dc01
ms.openlocfilehash: 4fa39a4d9369c84d2cffdaeff28dc9cb2f966b31
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370863"
---
# <a name="adding-multiple-views-to-a-single-document"></a>Tek Bir Belgeye Birden Çok Görünüm Ekleme

Microsoft Hazırlık Sınıfı (MFC) Kitaplığı ile oluşturulan tek belgeara (SDI) uygulamasında, her belge türü tek bir görünüm türüyle ilişkilidir. Bazı durumlarda, belgenin geçerli görünümünü yeni bir görünümle değiştirme yeteneğine sahip olmak istenir.

> [!TIP]
> Tek bir belge için birden çok görünüm uygulamayla ilgili ek yordamlar [COLLECT](../overview/visual-cpp-samples.md) için [Bkz.](../mfc/reference/cdocument-class.md#addview)

Görünümleri dinamik olarak varolan `CView`bir MFC uygulamasına geçirmek için yeni bir türetilmiş sınıf ve ek kod ekleyerek bu işlevselliği uygulayabilirsiniz.

Adımlar şu şekildedir:

- [Varolan Uygulama Sınıfını Değiştirme](#vcconmodifyexistingapplicationa1)

- [Yeni Görünüm Sınıfını Oluştur ve Değiştir](#vcconnewviewclassa2)

- [Yeni Görünüm Oluşturma ve Ekleme](#vcconattachnewviewa3)

- [Anahtarlama Işlevini Uygulayın](#vcconswitchingfunctiona4)

- [Görünümü Değiştirmek için Destek Ekle](#vcconswitchingtheviewa5)

Bu konunun geri kalanı aşağıdakileri varsayar:

- Türetilmiş `CWinApp`nesnenin adı `CMyWinApp`MYWINAPP'ta belirtilir ve `CMyWinApp` *tanımlanır. H* ve *MYWINAPP. CPP*.

- `CNewView`yeni `CView`türetilmiş nesnenin adıdır `CNewView` ve NEWVIEW'da bildirilir ve *tanımlanır. H* ve *NEWVIEW. CPP*.

## <a name="modify-the-existing-application-class"></a><a name="vcconmodifyexistingapplicationa1"></a>Varolan Uygulama Sınıfını Değiştirme

Uygulamanın görünümler arasında geçiş yapabilmek için, görünümleri depolamak için üye değişkenler ve bunları değiştirmek için bir yöntem ekleyerek uygulama sınıfını değiştirmeniz gerekir.

`CMyWinApp` MYWINAPP'taki bildirime aşağıdaki kodu *ekleyin. H*:

[!code-cpp[NVC_MFCDocViewSDI#1](../mfc/codesnippet/cpp/adding-multiple-views-to-a-single-document_1.h)]

Yeni üye değişkenleri `m_pOldView` `m_pNewView`ve , geçerli görünümü ve yeni oluşturulan bir işaret. Yeni yöntem`SwitchView`( ) kullanıcı tarafından istendiğinde görünümleri değiştirir. Yöntemin gövdesi daha sonra bu konuda [Anahtarlama Fonksiyonu Uygula'da](#vcconswitchingfunctiona4)ele alınmıştır.

Uygulama sınıfında yapılan son değişiklik, anahtarlama işlevinde kullanılan bir Windows iletisi **(WM_INITIALUPDATE)** tanımlayan yeni bir üstbilgi dosyası nın da dahil olmasını gerektirir.

MYWINAPP'ın dahil bölümüne aşağıdaki satırı *ekleyin. CPP*:

[!code-cpp[NVC_MFCDocViewSDI#2](../mfc/codesnippet/cpp/adding-multiple-views-to-a-single-document_2.cpp)]

Değişikliklerinizi kaydedin ve bir sonraki adıma geçin.

## <a name="create-and-modify-the-new-view-class"></a><a name="vcconnewviewclassa2"></a>Yeni Görünüm Sınıfını Oluştur ve Değiştir

Yeni görünüm sınıfını oluşturmak, Sınıf Görünümü'nden kullanılabilen **Yeni Sınıf** komutunu kullanarak kolay hale getirilir. Bu sınıfın tek `CView`şartı. Bu yeni sınıfı uygulamaya ekleyin. Projeye yeni bir sınıf ekleme hakkında özel bilgiler için [bkz.](../ide/adding-a-class-visual-cpp.md)

Sınıfı projeye ekledikten sonra, bazı görünüm sınıfı üyelerinin erişilebilirliğini değiştirmeniz gerekir.

*NEWVIEW'ı değiştirin. H,* yapı oluşturucu ve yıkıcı için **korumalıdan** **kamuya** erişim belirticisini değiştirerek. Bu, sınıfın dinamik olarak oluşturulmasını ve yok edilmesine ve görünür olmadan önce görünüm görünümünü değiştirmesine olanak tanır.

Değişikliklerinizi kaydedin ve bir sonraki adıma geçin.

## <a name="create-and-attach-the-new-view"></a><a name="vcconattachnewviewa3"></a>Yeni Görünüm Oluşturma ve Ekleme

Yeni görünüm oluşturmak ve eklemek için uygulama `InitInstance` sınıfınızın işlevini değiştirmeniz gerekir. Değişiklik, yeni bir görünüm nesnesi oluşturan ve sonra `m_pOldView` `m_pNewView` hem de varolan iki görünüm nesnesi ile baş harflerini yeni bir kod ekler.

`InitInstance` İşlev içinde yeni görünüm oluşturulduğundan, hem yeni hem de varolan görünümler uygulamanın ömrü boyunca devam eder. Ancak, uygulama gibi kolayca dinamik olarak yeni görünümü oluşturabilirsiniz.

Aramadan sonra bu kodu `ProcessShellCommand`ekleyin:

[!code-cpp[NVC_MFCDocViewSDI#3](../mfc/codesnippet/cpp/adding-multiple-views-to-a-single-document_3.cpp)]

Değişikliklerinizi kaydedin ve bir sonraki adıma geçin.

## <a name="implement-the-switching-function"></a><a name="vcconswitchingfunctiona4"></a>Anahtarlama Işlevini Uygulayın

Önceki adımda, yeni bir görünüm nesnesi oluşturan ve başharfe alan kod eklediniz. Son büyük parça anahtarlama yöntemini `SwitchView`uygulamaktır.

Uygulama sınıfı (MYWINAPP) için uygulama dosyasının*sonunda. CPP*), aşağıdaki yöntem tanımı ekleyin:

[!code-cpp[NVC_MFCDocViewSDI#4](../mfc/codesnippet/cpp/adding-multiple-views-to-a-single-document_4.cpp)]

Değişikliklerinizi kaydedin ve bir sonraki adıma geçin.

## <a name="add-support-for-switching-the-view"></a><a name="vcconswitchingtheviewa5"></a>Görünümü Değiştirmek için Destek Ekle

Son adım, uygulamanın görünümler arasında geçiş yapması gerektiğinde `SwitchView` yöntemi çağıran kod eklemeyi içerir. Bu çeşitli şekillerde yapılabilir: kullanıcının seçmesi için yeni bir menü öğesi ekleyerek veya belirli koşullar yerine getirildiğinde görünümleri dahili olarak değiştirerek.

Yeni menü öğeleri ve komut işleyicisi işlevleri ekleme hakkında daha fazla bilgi [için Komutlar ve Denetim Bildirimleri için İşleyiciler'e](../mfc/handlers-for-commands-and-control-notifications.md)bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Belge/Görünüm Mimarisi](../mfc/document-view-architecture.md)
