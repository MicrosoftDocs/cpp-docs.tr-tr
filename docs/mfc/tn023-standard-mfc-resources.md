---
title: 'TN023: Standart MFC kaynakları'
ms.date: 11/04/2016
f1_keywords:
- vc.mfc.resources
helpviewer_keywords:
- resources [MFC]
- TN023
- standard resources
ms.assetid: 60af8415-c576-4c2f-a711-ca5da0b9a1f2
ms.openlocfilehash: d29f0ab2254a52e01f2016f64a37ddfce47955bb
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "58780320"
---
# <a name="tn023-standard-mfc-resources"></a>TN023: Standart MFC kaynakları

Bu not ile sağlanan ve MFC kitaplık için gereken standart kaynakları açıklar.

## <a name="standard-resources"></a>Standart kaynaklar

MFC uygulamanızda kullanabileceğiniz önceden tanımlanmış kaynakları iki kategoriye sağlar: küçük resim kaynakları ve standart framework kaynakları.

Küçük resim, framework, bağlı değildir, ancak, uygulamanızın kullanıcı arabirimi eklemek isteyebileceğiniz ek kaynaklar kaynaklardır. Aşağıdaki küçük resim kaynakları MFC genel örnekte bulunan [küçük](../overview/visual-cpp-samples.md):

- Common.rc: Tek bir içeren dosyayı kaynak:

   - Çeşitli iş ve veri işleme görevleri temsil eden simgeler, büyük bir koleksiyonu.

   - Birçok ortak İmleçler (Ayrıca bkz: Afxres.rc).

   - Birkaç araç çubuğu düğmeleri içeren bir araç çubuğu bit eşlem.

   - Commdlg.dll tarafından kullanılan bit eşlem ve simge kaynaklar.

- Indicate.rc: Durum çubuğu anahtar durumu göstergeleri Caps Lock "sınır" gibi için dize kaynakları içerir.

- Prompts.rc: Id_fıle_new için "Yeni belge oluştur" gibi önceden tanımlanmış her komut istemi menü dize kaynakları içerir.

- COMMDLG.rc: Standart COMMDLG iletişim kutusu şablonları içeren bir Visual C++ uyumlu bir .rc dosyası.

Standart framework kaynakları ve iç uygulamaları framework bağımlı AFX tanımlı kimlikleri kaynaklardır. Nadiren bu AFX tarafından tanımlanan kaynakları değiştirmeniz de gerekecektir. Bunu yaparsanız, bu konunun ilerleyen bölümlerinde açıklanan yordamı izlemelisiniz.

Aşağıdaki framework kaynakları MFC\INCLUDE dizinde bulunur:

- Afxres.rc: Framework tarafından kullanılan ortak kaynaklar.

- Afxprınt.rc: Yazdırmaya özel kaynaklar.

- Afxolecl.rc: OLE istemci uygulamaları için belirli kaynaklar.

- Afxolev.rc: Tüm OLE sunucu uygulamaları için belirli kaynaklar.

## <a name="using-clip-art-resources"></a>Küçük resim kaynakları kullanma

#### <a name="to-use-a-clip-art-binary-resource"></a>Bir küçük resim ikili kaynak kullanmak için

1. Visual c++'ta, uygulamanızın kaynak dosyasını açın.

1. Common.rc açın. Bu dosya, tüm ikili küçük resim kaynakları içerir. Common.rc dosya derlendiğinden bu biraz zaman alabilir.

1. Uygulamanızın kaynak dosyasına Common.rc kullanmak istediğiniz kaynakları sürüklerken CTRL tuşunu basılı tutun.

Diğer küçük resim kaynakları kullanmak için aynı adımları izleyin. Tek fark, Common.rc yerine uygun .rc dosyasını açar.

> [!NOTE]
>  Yanlışlıkla Common.rc kaynakları kalıcı olarak taşıyamazsınız dikkat edin. Kaynakları sürüklerken CTRL tuşunu basılı tutun, bir kopyasını oluşturur. Sürüklerken CTRL basılı değil, kaynakları taşınır. Yanlışlıkla değişiklik Common.rc dosyaya yaptığınız endişeleriniz varsa, Common.rc için değişikliklerin kaydedilip edilmeyeceğini sorulduğunda "Hayır"'i tıklatın.

> [!NOTE]
>  .Rc kaynak dosyası özel bir TEXTINCLUDE kaynak yanlışlıkla standart .rc dosyaları üzerine kaydetmesini engeller bunlara sahip.

### <a name="customizing-standard-framework-resources"></a>Standart Framework kaynakları ve özelleştirme

Standart framework kaynakları ve genellikle dahil edilecek bir uygulamada kullanarak # uygulama kaynak dosyasına komut include. AppWizard kaynak dosyası oluşturur. Bu dosya seçtiğiniz hangi AppWizard seçeneklere bağlı olarak uygun standart framework kaynakları içerir. Gözden geçirin, ekleyebilir veya derleme zamanı yönergeleri değiştirerek kaynakları dahil kaldırabilirsiniz. Bunu yapmak için açık **kaynak** menü ve select **dahil edilenleri Ayarla**. Öğeyi Düzenle "Derleme zamanı yönergeleri" bakın. Örneğin:

```
#include "afxres.rc"
#include "afxprint.rc"
```

Standart framework kaynakları özelleştirilmesine en sık karşılaşılan durum ekleyerek veya ek kaldırma içerir, yazdırma için OLE istemci ve OLE sunucusu desteği.

Standart framework kaynakları ve belirli uygulamanızın içeriğini özelleştirmek için isteyebileceğiniz bazı nadir durumlarda yalnızca ekleyin ve dosyanın tamamını kaldırın. Aşağıdakilere adımları nasıl dahil olan kaynaklarla sınırlayabilirsiniz göster:

##### <a name="to-customize-the-contents-of-a-standard-resource-file"></a>Standart kaynak dosyasının içeriğini özelleştirmek için

1. Visual C++'da kaynak dosyasını açın.

1. Kaynak dahil edilenleri Ayarla komutunu kullanarak kaldırma `#include` özelleştirmek istediğiniz standart .rc dosyası için. Örneğin, Baskı Önizleme araç özelleştirmek için kaldırmak `#include "afxprint.rc"` satır.

1. Uygun standart kaynak dosyaları içinde MFC\INCLUDE açın. Örnek bu konunun önceki kısımlarında, uygun MFC\Include\Aafxprint.rc dosyasıdır

1. Tüm kaynakları standart .rc dosyasından uygulama kaynak dosyasına kopyalayın.

1. Standart kaynakları uygulama kaynak dosyasının kopyasını değiştirin.

> [!NOTE]
>  Doğrudan standart .rc dosyalarındaki kaynaklar değiştirmeyin. Bunun yapılması her uygulamada, yalnızca üzerinde çalıştığınız bir kullanılabilir kaynakları değiştirir.

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya Göre Teknik Notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)
