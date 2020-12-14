---
description: Hakkında daha fazla bilgi edinin:/WHOLEARCHIVE (tüm kitaplık nesnesi dosyalarını dahil et)
title: /WHOLEARCHIVE (tüm kitaplık nesnesi dosyalarını dahil et)
ms.date: 02/12/2020
ms.assetid: ee92d12f-18af-4602-9683-d6223be62ac9
ms.openlocfilehash: 1cbc2ad29bab124af90551d2f4a96ee9f08c578c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97259181"
---
# <a name="wholearchive-include-all-library-object-files"></a>/WHOLEARCHIVE (tüm kitaplık nesnesi dosyalarını dahil et)

Bağlayıcıyı, bağlı çalıştırılabilirteki statik kitaplığa tüm nesne dosyalarını dahil etmek için zorlayın.

## <a name="syntax"></a>Syntax

> **/WHOLEARCHIVE**\
> **/WHOLEARCHIVE:**_kitaplık_

### <a name="arguments"></a>Arguments

*Kitaplığı*\
Statik kitaplık için isteğe bağlı bir yol adı. Bağlayıcı, bu kitaplıktan her nesne dosyasını içerir.

## <a name="remarks"></a>Açıklamalar

/WHOLEARCHIVE seçeneği, bağlayıcıyı belirtilen bir statik kitaplıktan her nesne dosyasını içerecek şekilde veya hiçbir kitaplık belirtilmemişse, belirtilen tüm statik kitaplıklardan bağlantı komutuna dahil etmek üzere zorlar. Birden çok kitaplık için/WHOLEARCHIVE seçeneğini belirtmek için bağlayıcı komut satırında birden fazla/WHOLEARCHIVE anahtarı kullanabilirsiniz. Varsayılan olarak, bağlayıcı yalnızca çalıştırılabilirteki diğer nesne dosyaları tarafından başvurulan sembolleri dışa aktardıklarında, bağlantılı çıktıda nesne dosyalarını içerir. /WHOLEARCHIVE seçeneği, bağlayıcının bir statik kitaplıkta arşivlenmiş tüm nesne dosyalarını bağlayıcı komut satırında tek tek belirtildikleri gibi işleme almasını sağlar.

/WHOLEARCHIVE seçeneği, bir statik kitaplıktan tüm sembolleri yeniden dışarı aktarmak için kullanılabilir. Bu, birden çok statik kitaplıktan bir bileşen oluşturduğunuzda tüm kitaplık kodunuzun, kaynaklarınızın ve meta verilerinizin eklendiğinden emin olmanızı sağlar. Dışarı aktarma için Windows Çalışma Zamanı bileşenleri içeren bir statik kitaplık oluştururken uyarı LNK4264 görürseniz, bu kitaplığı başka bir bileşen veya uygulamaya bağlarken/WHOLEARCHIVE seçeneğini kullanın.

/WHOLEARCHIVE seçeneği Visual Studio 2015 güncelleştirme 2 ' de eklenmiştir.

### <a name="to-set-this-linker-option-in-visual-studio"></a>Visual Studio 'da bu bağlayıcı seçeneğini ayarlamak için

1. Proje **Özellik sayfaları** iletişim kutusunu açın. Daha fazla bilgi için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**, **bağlayıcı** altında **komut satırı** özellik sayfasını seçin.

1. **Ek seçenekler** metin kutusuna/WHOLEARCHIVE seçeneğini ekleyin.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)
