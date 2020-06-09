---
title: 'Pano: Veri Kopyalama ve Yapıştırma'
ms.date: 11/04/2016
helpviewer_keywords:
- Clipboard, copying data to
- Clipboard, pasting
ms.assetid: 580e10be-241f-4f9f-94cf-8302edc5beef
ms.openlocfilehash: ed3056ec4fb3d3098870a03522d3bf17f41fbe34
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84620699"
---
# <a name="clipboard-copying-and-pasting-data"></a>Pano: Veri Kopyalama ve Yapıştırma

Bu konu başlığı altında, OLE uygulamanızda Pano 'Ya kopyalamayı ve yapıştırmayı uygulamak için gereken en düşük iş açıklanmaktadır. Devam etmeden önce [veri nesneleri ve veri kaynakları (OLE)](data-objects-and-data-sources-ole.md) konularını okumanız önerilir.

Kopyalama veya yapıştırmayı uygulayabilmeniz için önce, düzenleme menüsünde kopyalama, kesme ve yapıştırma seçeneklerini işleyecek işlevler sağlamalısınız.

## <a name="copying-or-cutting-data"></a><a name="_core_copying_or_cutting_data"></a>Verileri kopyalama veya kesme

#### <a name="to-copy-data-to-the-clipboard"></a>Verileri panoya kopyalamak için

1. Kopyalanacak verilerin yerel veriler olup olmadığını veya gömülü veya bağlantılı bir öğe olduğunu belirleme.

   - Veriler katıştırılmışsa veya bağlanmışsa, seçilen nesneye bir işaretçi alın `COleClientItem` .

   - Veriler yerel ise ve uygulama bir sunucu ise, seçili verileri içeren yeni bir nesne oluşturun `COleServerItem` . Aksi takdirde, `COleDataSource` veriler için bir nesne oluşturun.

1. Seçili öğenin `CopyToClipboard` üye işlevini çağırın.

1. Kullanıcı kopyalama işlemi yerine kesme işlemi seçerse, seçili verileri uygulamanızdan silin.

Bu sıranın bir örneğini görmek için `OnEditCut` `OnEditCopy` MFC OLE örnek programlar [Oclient](../overview/visual-cpp-samples.md) ve [hiersvr](../overview/visual-cpp-samples.md)içindeki ve işlevlerine bakın. Bu örneklerin Şu anda seçili olan verilere yönelik bir işaretçi korudığına, 1. adım zaten tamamlanmış olduğunu unutmayın.

## <a name="pasting-data"></a><a name="_core_pasting_data"></a>Verileri yapıştırma

Verileri yapıştırmaktan daha karmaşıktır çünkü verileri uygulamanıza yapıştırmada kullanılacak biçimi seçmeniz gerekir.

#### <a name="to-paste-data-from-the-clipboard"></a>Panodan veri yapıştırmak için

1. Görünüm sınıfınıza, `OnEditPaste` düzenleme menüsünden Yapıştır seçeneğini belirleyerek kullanıcıları işlemek için uygulamasını uygulayın.

1. `OnEditPaste`İşlevinde, bir `COleDataObject` nesne oluşturun ve `AttachClipboard` Bu nesneyi panodaki verilere bağlamak için üye işlevini çağırın.

1. `COleDataObject::IsDataAvailable`Belirli bir biçimin kullanılabilir olup olmadığını denetlemek için çağırın.

   Alternatif olarak, `COleDataObject::BeginEnumFormats` uygulamanız için en uygun olanı bulana kadar diğer biçimleri aramak için kullanabilirsiniz.

1. Biçimin yapıştırmayı gerçekleştirin.

Bunun nasıl çalıştığına ilişkin bir örnek için, `OnEditPaste` MFC OLE örnek programları [oclient](../overview/visual-cpp-samples.md) ve [hiersvr](../overview/visual-cpp-samples.md)'de tanımlanan görünüm sınıflarında üye işlevlerinin uygulanmasına bakın.

> [!TIP]
> Yapıştırma işleminin kendi işlevine ayrılmanın başlıca avantajı, bir sürükle ve bırak işlemi sırasında uygulamanızda veri bırakıldığında aynı yapıştırma kodunun kullanılabilir olmasını sağlayabilir. OCLIENT ve HIERSVR gibi `OnDrop` işleviniz, `DoPasteItem` yapıştırma işlemlerini uygulamak için yazılan kodu yeniden kullanarak da çağırabilir.

Düzenle menüsünde Özel Yapıştır seçeneğini işlemek için [OLE 'deki konu Iletişim kutularına](dialog-boxes-in-ole.md)bakın.

### <a name="what-do-you-want-to-know-more-about"></a>Hakkında daha fazla bilgi edinmek istiyorsunuz

- [Diğer biçimleri ekleme](clipboard-adding-other-formats.md)

- [OLE veri nesneleri ve veri kaynakları ve Tekdüzen veri aktarımı](data-objects-and-data-sources-ole.md)

- [OLE sürükle ve bırak](drag-and-drop-ole.md)

- [OLE](ole-background.md)

## <a name="see-also"></a>Ayrıca bkz.

[Pano: OLE Pano Mekanizmasını Kullanma](clipboard-using-the-ole-clipboard-mechanism.md)
