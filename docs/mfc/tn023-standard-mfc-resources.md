---
description: 'Hakkında daha fazla bilgi edinin: TN023: Standart MFC kaynakları'
title: 'TN023: Standart MFC Kaynakları'
ms.date: 11/04/2016
helpviewer_keywords:
- resources [MFC]
- TN023
- standard resources
ms.assetid: 60af8415-c576-4c2f-a711-ca5da0b9a1f2
ms.openlocfilehash: 8a78a029d67920b7cd711be6200ccced86d243e3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97215774"
---
# <a name="tn023-standard-mfc-resources"></a>TN023: Standart MFC Kaynakları

Bu notta, MFC kitaplığı tarafından sağlanmış ve gereken standart kaynaklar açıklanmaktadır.

## <a name="standard-resources"></a>Standart kaynaklar

MFC, uygulamanızda kullanabileceğiniz, önceden tanımlanmış iki kaynak kategorisi sunar: küçük resim kaynakları ve standart çerçeve kaynakları.

Küçük resim kaynakları, Framework 'ün bağımlı olmadığı, ancak uygulamanızın kullanıcı arabirimine eklemek isteyebileceğiniz ek kaynaklardır. Aşağıdaki küçük resim kaynakları MFC genel örnek [küçük](../overview/visual-cpp-samples.md)resimlere dahil edilir:

- Common. rc: şunları içeren tek bir kaynak dosyası:

  - Çeşitli iş ve veri işleme görevlerini temsil eden büyük bir simgeler koleksiyonu.

  - Birkaç ortak imleçler (Ayrıca bkz. afxres. RC).

  - Çeşitli araç çubuğu düğmeleri içeren bir araç çubuğu bit eşlemi.

  - Commdlg.dll tarafından kullanılan bit eşlem ve simge kaynakları.

- . RC belirtin: Caps Lock için "CAP" gibi durum çubuğu anahtar durumu göstergeleri için dize kaynakları Içerir.

- İstemler. rc: ID_FILE_NEW için "yeni belge oluştur" gibi, önceden tanımlanmış her komut için Menü istemi dize kaynaklarını Içerir.

- Commdlg. rc: Standart COMMDLG iletişim şablonlarını içeren Visual C++ uyumlu bir. rc dosyası.

Standart çerçeve kaynakları, çerçevesinin iç uygulamalar için bağımlı olduğu AFX tanımlı kimlikleri olan kaynaklardır. Bu AFX tanımlı kaynakları nadiren değiştirmeniz gerekir. Bunu yaparsanız, bu konunun ilerleyen kısımlarında açıklanan yordamı izlemeniz gerekir.

Aşağıdaki çerçeve kaynakları MFC\INCLUDE dizininde yer alır:

- Afxres. rc: Framework tarafından kullanılan ortak kaynaklar.

- Afxprint. rc: yazdırmaya özel kaynaklar.

- Afxolecl. rc: OLE istemci uygulamalarına özel kaynaklar.

- Afxolev. rc: tam OLE sunucusu uygulamalarına özel kaynaklar.

## <a name="using-clip-art-resources"></a>Clip-Art kaynaklarını kullanma

#### <a name="to-use-a-clip-art-binary-resource"></a>Küçük resim ikili kaynağını kullanmak için

1. Uygulamanızın kaynak dosyasını Visual C++ açın.

1. Ortak. RC 'yi açın. Bu dosya, tüm ikili küçük resim kaynaklarını içerir. Common. rc dosyası derlendiği için bu işlem biraz zaman alabilir.

1. Common. RC 'den uygulamanızın kaynak dosyasına kullanmak istediğiniz kaynakları sürüklerken CTRL tuşunu basılı tutun.

Diğer küçük resim kaynaklarını kullanmak için aynı adımları izleyin. Tek fark, Common. RC yerine uygun. rc dosyasını açmanızdır.

> [!NOTE]
> Kaynakları yanlışlıkla ortak. rc dosyasından kalıcı olarak taşımamaya dikkat edin. Kaynakları sürüklerken CTRL tuşunu basılı tutarsanız bir kopya oluşturacaksınız. Sürüklerken CTRL tuşunu basılı tutmanız durumunda kaynaklar taşınır. Ortak. rc dosyasında yanlışlıkla değişiklikler yapmış olabileceğiniz konusunda endişe ediyorsanız, değişiklikleri Common. rc dosyasına kaydedip kaydetmeyeceğinizi sorulduğunda "Hayır" a tıklayın.

> [!NOTE]
> . RC kaynak dosyalarının, standart. RC dosyalarının üzerine yanlışlıkla kaydedilmesini engelleyecek özel bir TEXTıNCLUDE kaynağı vardır.

### <a name="customizing-standard-framework-resources"></a>Standart çerçeve kaynaklarını özelleştirme

Standart çerçeve kaynakları, genellikle uygulamanın kaynak dosyasındaki #include komutu kullanılarak bir uygulamaya eklenir. AppWizard bir kaynak dosyası oluşturacaktır. Bu dosya, seçtiğiniz AppWizard seçeneklerine bağlı olarak uygun standart çerçeve kaynaklarını içerir. Derleme zamanı yönergelerini değiştirerek hangi kaynakların dahil edildiğini gözden geçirebilir, ekleyebilir veya kaldırabilirsiniz. Bunu yapmak için **kaynak** menüsünü açın ve **eklemeleri ayarla**' yı seçin. "Derleme zamanı yönergeleri" düzenleme öğesi bölümüne bakın. Örneğin:

```
#include "afxres.rc"
#include "afxprint.rc"
```

Standart çerçeve kaynaklarını özelleştirmenin en yaygın durumu, yazdırma, OLE Istemcisi ve OLE sunucu desteği için ek içerir ekleme veya kaldırma.

Nadir durumlarda, belirli bir uygulama için standart çerçeve kaynaklarının içeriğini özelleştirmek isteyebilirsiniz, yalnızca tüm dosyayı ekleyip kaldırın. Bu adımlarda, dahil edilen kaynakları nasıl sınırlayacakları gösterilmektedir:

##### <a name="to-customize-the-contents-of-a-standard-resource-file"></a>Standart kaynak dosyasının içeriğini özelleştirmek için

1. Kaynak dosyasını Visual C++ açın.

1. Kaynak kümesi Içerir komutunu kullanarak `#include` özelleştirmek istediğiniz standart. rc dosyası için öğesini kaldırın. Örneğin, baskı önizleme araç çubuğunu özelleştirmek için `#include "afxprint.rc"` çizgiyi kaldırın.

1. MFC\INCLUDEIÇINDE uygun standart kaynak dosyalarını açın. Bu konunun önceki kısımlarında yer alan aşağıdaki örnekte, uygun dosya Mfc\include\aafxprint.exe şeklindedir

1. Standart. RC dosyasındaki tüm kaynakları uygulama kaynak dosyanıza kopyalayın.

1. Uygulama kaynak dosyanızdaki standart kaynakların kopyasını değiştirin.

> [!NOTE]
> Kaynakları doğrudan standart. RC dosyalarında değiştirmeyin. Bunun yapılması, yalnızca şu anda üzerinde çalıştığınız bir uygulamada değil, her uygulamadaki kullanılabilir kaynakları değiştirir.

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya göre teknik notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye göre teknik notlar](../mfc/technical-notes-by-category.md)
