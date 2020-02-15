---
title: /WHOLEARCHIVE (tüm kitaplık nesnesi dosyalarını dahil et)
ms.date: 02/12/2020
ms.assetid: ee92d12f-18af-4602-9683-d6223be62ac9
ms.openlocfilehash: 95685c9c0dfde45c42449bbcad67228a0e21b36a
ms.sourcegitcommit: 8414cd91297dea88c480e208c7b5301db9972f19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2020
ms.locfileid: "77257539"
---
# <a name="wholearchive-include-all-library-object-files"></a>/WHOLEARCHIVE (tüm kitaplık nesnesi dosyalarını dahil et)

Bağlayıcıyı, bağlı çalıştırılabilirteki statik kitaplığa tüm nesne dosyalarını dahil etmek için zorlayın.

## <a name="syntax"></a>Sözdizimi

> **/WHOLEARCHIVE**\
> **/WHOLEARCHIVE:** _kitaplık_

### <a name="arguments"></a>Bağımsız Değişkenler

*kitaplık*\
Statik kitaplık için isteğe bağlı bir yol adı. Bağlayıcı, bu kitaplıktan her nesne dosyasını içerir.

## <a name="remarks"></a>Açıklamalar

/WHOLEARCHIVE seçeneği, bağlayıcıyı belirtilen bir statik kitaplıktan her nesne dosyasını içerecek şekilde veya hiçbir kitaplık belirtilmemişse, belirtilen tüm statik kitaplıklardan bağlantı komutuna dahil etmek üzere zorlar. Birden çok kitaplık için/WHOLEARCHIVE seçeneğini belirtmek için bağlayıcı komut satırında birden fazla/WHOLEARCHIVE anahtarı kullanabilirsiniz. Varsayılan olarak, bağlayıcı yalnızca çalıştırılabilirteki diğer nesne dosyaları tarafından başvurulan sembolleri dışa aktardıklarında, bağlantılı çıktıda nesne dosyalarını içerir. /WHOLEARCHIVE seçeneği, bağlayıcının bir statik kitaplıkta arşivlenmiş tüm nesne dosyalarını bağlayıcı komut satırında tek tek belirtildikleri gibi işleme almasını sağlar.

/WHOLEARCHIVE seçeneği, bir statik kitaplıktan tüm sembolleri yeniden dışarı aktarmak için kullanılabilir. Bu, birden çok statik kitaplıktan bir bileşen oluşturduğunuzda tüm kitaplık kodunuzun, kaynaklarınızın ve meta verilerinizin eklendiğinden emin olmanızı sağlar. Dışarı aktarma için Windows Çalışma Zamanı bileşenleri içeren bir statik kitaplık oluştururken uyarı LNK4264 görürseniz, bu kitaplığı başka bir bileşen veya uygulamaya bağlarken/WHOLEARCHIVE seçeneğini kullanın.

/WHOLEARCHIVE seçeneği Visual Studio 2015 güncelleştirme 2 ' de eklenmiştir.

### <a name="to-set-this-linker-option-in-visual-studio"></a>Visual Studio 'da bu bağlayıcı seçeneğini ayarlamak için

1. Proje **Özellik sayfaları** iletişim kutusunu açın. Daha fazla bilgi için bkz [. C++ Visual Studio 'da derleyici ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**, **bağlayıcı**altında **komut satırı** özellik sayfasını seçin.

1. **Ek seçenekler** metin kutusuna/WHOLEARCHIVE seçeneğini ekleyin.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC Bağlayıcı Seçenekleri](linker-options.md)
