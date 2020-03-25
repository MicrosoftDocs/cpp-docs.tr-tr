---
title: Önemli hata C1010
ms.date: 09/03/2019
f1_keywords:
- C1010
helpviewer_keywords:
- C1010
ms.assetid: dfd035f1-a7a2-40bc-bc92-dc4d7f456767
ms.openlocfilehash: 40a2828ce6b21384ec49c371f23e506d816f1284
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80204795"
---
# <a name="fatal-error-c1010"></a>Önemli hata C1010

> önceden derlenmiş üst bilgi aranırken beklenmeyen dosya sonu. Kaynağınıza ' #include *Name*' eklemeyi mi unuttunuz?

## <a name="remarks"></a>Açıklamalar

[/Yu](../../build/reference/yu-use-precompiled-header-file.md) tarafından belirtilen bir içerme dosyası kaynak dosyada listelenmez. Birçok Visual Studio C++ proje türünde bu seçenek varsayılan olarak etkindir. Bu seçenekle belirtilen varsayılan içerme dosyası, Visual Studio 2017 ve önceki sürümlerde *pch. h*veya *stdadfx. h* ' dir.

Visual Studio ortamında, bu hatayı çözmek için aşağıdaki yöntemlerden birini kullanın:

- Yanlışlıkla, *pch. h* üstbilgi dosyasını veya *pch. cpp* kaynak dosyasını geçerli projeden sildiğinizden, yeniden adlandırmadığınızdan veya kaldırdığınızdan emin olun. (Eski projelerde bu dosyalar *stbafx. h* ve *stdadfx. cpp*olarak adlandırılabilir.)

- Kaynak dosyalarınızda diğer kod veya Önişlemci yönergelerinden önce *pch. h* veya *stdadfx. h* üstbilgi dosyasının eklendiğinden emin olun. (Visual Studio 'da Bu üstbilgi dosyası, **ön derlenmiş üstbilgi dosyası** proje özelliği tarafından belirtilir.)

- Ön derlenmiş üstbilgi kullanımını devre dışı bırakabilirsiniz. Önceden derlenmiş üstbilgileri kapatırsanız, derleme performansını ciddi bir şekilde etkileyebilir.

### <a name="to-turn-off-precompiled-headers"></a>Önceden derlenmiş üstbilgileri devre dışı bırakmak için

Bir projede önceden derlenmiş üst bilgi kullanımını devre dışı bırakmak için şu adımları izleyin:

1. **Çözüm Gezgini** penceresinde, proje adına sağ tıklayın ve ardından **Özellikler** ' i seçerek Proje **Özellik sayfaları** iletişim kutusunu açın.

1. **Yapılandırma** açılır penceresinde **tüm yapılandırmalar**' ı seçin.

1. **Yapılandırma özellikleri** > **C/C++**  > **önceden derlenmiş üstbilgiler** özellik sayfasını seçin.

1. Özellik listesinde, **önceden derlenmiş üst bilgi** özelliği için açılan listeyi seçin ve ardından **önceden derlenmiş üst bilgileri kullanmayın**' ı seçin. Değişikliklerinizi kaydetmek için **Tamam ' ı** seçin.

1. **Çözüm Gezgini** penceresinde, projenizdeki *pch. cpp* kaynak dosyasına sağ tıklayın. (Eski projelerde, dosya *stbafx. cpp*olarak adlandırılmış olabilir.) Derlemeden kaldırmak için **projeden hariç tut** ' ı seçin.

1. Oluşturduğunuz her yapılandırma için **derleme** > **Temizleme çözümü** menü komutunu kullanın, ara derleme dizinlerinizde *Project_Name. pch* dosyalarını silebilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Ön derlenmiş üstbilgi dosyaları](../../build/creating-precompiled-header-files.md)\
[/Yıc (ön derlenmiş üstbilgi dosyası oluştur)](../../build/reference/yc-create-precompiled-header-file.md)\
[/Yu (önceden derlenmiş üst bilgi dosyasını kullan)](../../build/reference/yu-use-precompiled-header-file.md)
