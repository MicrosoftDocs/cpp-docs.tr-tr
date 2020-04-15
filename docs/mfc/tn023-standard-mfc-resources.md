---
title: 'TN023: Standart MFC Kaynakları'
ms.date: 11/04/2016
helpviewer_keywords:
- resources [MFC]
- TN023
- standard resources
ms.assetid: 60af8415-c576-4c2f-a711-ca5da0b9a1f2
ms.openlocfilehash: 90e7b9b7c354ba919c3dee279725b4498bea57ff
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370376"
---
# <a name="tn023-standard-mfc-resources"></a>TN023: Standart MFC Kaynakları

Bu not, MFC kitaplığı tarafından sağlanan ve gereken standart kaynakları açıklar.

## <a name="standard-resources"></a>Standart Kaynaklar

MFC, uygulamanızda kullanabileceğiniz iki önceden tanımlanmış kaynak kategorisi sunar: küçük resim kaynakları ve standart çerçeve kaynakları.

Küçük resim kaynakları, çerçevenin bağlı olmadığı, ancak uygulamanızın kullanıcı arabirimine eklemek isteyebileceğin ek kaynaklardır. Aşağıdaki küçük-resim kaynakları MFC Genel örnek [CLIPART'ta](../overview/visual-cpp-samples.md)yer almaktadır:

- Common.rc: Aşağıdakileri içeren tek bir kaynak dosyası:

  - Çeşitli iş ve veri işleme görevlerini temsil eden büyük bir simge koleksiyonu.

  - Birkaç ortak imleçler (ayrıca Afxres.rc bakınız).

  - Birkaç araç çubuğu düğmesi içeren bir araç çubuğu biteşlemi.

  - Commdlg.dll tarafından kullanılan bit eşlemi ve simge kaynakları.

- Indicate.rc: Caps Lock için "CAP" gibi durum çubuğu anahtar durumu göstergeleri için dize kaynakları içerir.

- Prompts.rc: ID_FILE_NEW için "Yeni bir belge oluşturma" gibi önceden tanımlanmış her komut için menü istemi dize kaynaklarını içerir.

- Commdlg.rc: Standart COMMDLG iletişim şablonlarını içeren Görsel C++ uyumlu .rc dosyası.

Standart çerçeve kaynakları, çerçevenin iç uygulamalar için bağlı olduğu AFX tanımlı iD'lere sahip kaynaklardır. Bu AFX tanımlı kaynakları nadiren değiştirmeniz gerekir. Bunu yaparsanız, bu konuda daha sonra özetlenen yordamı izlemeniz gerekir.

Aşağıdaki çerçeve kaynakları MFC\INCLUDE dizininde yer alır:

- Afxres.rc: Çerçeve tarafından kullanılan ortak kaynaklar.

- Afxprint.rc: Yazdırmaya özel kaynaklar.

- Afxolecl.rc: OLE istemci uygulamalarına özgü kaynaklar.

- Afxolev.rc: Tam OLE sunucu uygulamalarına özgü kaynaklar.

## <a name="using-clip-art-resources"></a>Küçük Resim Kaynaklarını Kullanma

#### <a name="to-use-a-clip-art-binary-resource"></a>Küçük resimli ikili kaynak kullanmak için

1. Uygulamanızın kaynak dosyanı Visual C++'da açın.

1. Common.rc'yi açın. Bu dosya tüm ikili küçük resim kaynaklarını içerir. Common.rc dosyası derlenmiş olduğundan bu işlem biraz zaman alabilir.

1. Kullanmak istediğiniz kaynakları Common.rc'den uygulamanızın kaynak dosyasına sürüklerken CTRL'yi basılı tutun.

Diğer küçük resim kaynaklarını kullanmak için aynı adımları izleyin. Tek fark, Common.rc yerine uygun .rc dosyasını açacağınızdır.

> [!NOTE]
> Kaynakları istemeden Common.rc'den kalıcı olarak çıkarmamaya dikkat edin. Kaynakları sürüklerken CTRL tuşunu tutarsanız, bir kopyasını oluşturursunuz. Sürüklerken CTRL'yi basılı tutmazsanız, kaynaklar taşınır. Common.rc dosyasında yanlışlıkla değişiklik yapmış olabileceğiniz konusunda endişeleriniz varsa, değişiklikleri Common.rc'ye kaydedip kaydetmediğiniz sorulduğunda "Hayır"ı tıklayın.

> [!NOTE]
> .rc kaynak dosyaları, standart .rc dosyalarının üzerine yanlışlıkla kaydetmenizi engelleyecek özel bir TEXTINCLUDE kaynağına sahiptir.

### <a name="customizing-standard-framework-resources"></a>Standart Çerçeve Kaynaklarını Özelleştirme

Standart çerçeve kaynakları genellikle bir uygulamanın kaynak dosyasındaki #include komutu kullanılarak bir uygulamaya dahil edilir. AppWizard bir kaynak dosyası oluşturur. Bu dosya, seçtiğiniz AppWizard seçeneklerine bağlı olarak uygun standart çerçeve kaynaklarını içerir. Derleme zamanı yönergelerini değiştirerek hangi kaynakların dahil edildiğini gözden geçirebilir, ekleyebilir veya kaldırabilirsiniz. Bunu yapmak için **Kaynak** menüsünü açın ve **Içerir'i seçin.** "Derleme-Zaman Yönergeleri" edit öğesine bakın. Örneğin:

```
#include "afxres.rc"
#include "afxprint.rc"
```

Standart çerçeve kaynaklarını özelleştirmenin en yaygın örneği yazdırma, OLE Client ve OLE Server desteği için ek içerir ekleme veya kaldırmadır.

Bazı nadir durumlarda, dosyanın tamamını eklemek ve kaldırmakla değil, belirli uygulamanız için standart çerçeve kaynaklarının içeriğini özelleştirmek isteyebilirsiniz. Aşağıdaki adımlar, dahil edilen kaynakları nasıl sınırlayabileceğinizi gösterir:

##### <a name="to-customize-the-contents-of-a-standard-resource-file"></a>Standart kaynak dosyasının içeriğini özelleştirmek için

1. Kaynak dosyasını Visual C++'da açın.

1. Kaynak Kümesi Içerir komutunu `#include` kullanarak, özelleştirmek istediğiniz standart .rc dosyasını kaldırın. Örneğin, yazdırma önizleme araç çubuğunu `#include "afxprint.rc"` özelleştirmek için satırı kaldırın.

1. MFC\INCLUDE'da uygun standart kaynak dosyalarını açın. Bu konunun önceki örneklerini izleyerek, uygun dosya MFC\Include\Aafxprint.rc

1. Standart .rc dosyasındaki tüm kaynakları uygulama kaynak dosyanıza kopyalayın.

1. Uygulama kaynak dosyanızdaki standart kaynakların kopyasını değiştirin.

> [!NOTE]
> Kaynakları doğrudan standart .rc dosyalarında değiştirmeyin. Bunu yapmak, yalnızca üzerinde çalıştığınız uygulamada değil, her uygulamada bulunan kaynakları değiştirir.

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya Göre Teknik Notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)
