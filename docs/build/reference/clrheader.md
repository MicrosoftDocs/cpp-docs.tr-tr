---
title: /CLRHEADER
ms.date: 11/04/2016
f1_keywords:
- /CLRHEADER
helpviewer_keywords:
- -CLRHEADER dumpbin option
- /CLRHEADER dumpbin option
- CLRHEADER dumpbin option
ms.assetid: cf73424f-4541-47e2-b94e-69b95266ef2a
ms.openlocfilehash: 864ecc0063716ce712e28b063714ce7c17fc294a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50627376"
---
# <a name="clrheader"></a>/CLRHEADER

CLR özel bilgileri görüntüler.

## <a name="syntax"></a>Sözdizimi

> / CLRHEADER *dosyası*

### <a name="arguments"></a>Arguments

|||
|-|-|
*Dosya*| Bir resim dosyası ile oluşturulmuş [/CLR](../../build/reference/clr-common-language-runtime-compilation.md).

## <a name="remarks"></a>Açıklamalar

**/ CLRHEADER** herhangi bir yönetilen programında kullanılan .NET üst bilgileri hakkındaki bilgileri görüntüler. Çıktı, .NET üstbilgi ve bölümleri üst bilgisindeki bayt cinsinden boyutunu ve konumunu gösterir.

Yalnızca [OPTIONAL](../../build/reference/headers.md) DUMPBIN seçeneği ile üretilen dosyalar kullanıma [/GL](../../build/reference/gl-whole-program-optimization.md) derleyici seçeneği.

Zaman **/CLRHEADER** kullanılan/CLR ile derlenen bir dosyada olacaktır bir **clr üst bilgi:** dumpbin çıkış bölümünde. Değerini **bayrakları** hangi/CLR seçeneği kullanılan gösterir:

- 0 – / CLR (yerel kod görüntü içerebilir).

Görüntüyü bir ortak dil çalışma zamanı için oluşturulmuş programlama yoluyla da kontrol edebilirsiniz.  Daha fazla bilgi için [nasıl yapılır: görüntü yerel mi yoksa CLR mi belirlemek](../../dotnet/how-to-determine-if-an-image-is-native-or-clr.md).

**/CLR: pure** ve **/CLR: safe** derleyici seçenekleri Visual Studio 2015'te kullanım dışı ve Visual Studio 2017'de desteklenmiyor. "Saf" veya "güvenli" olmalıdır kod unity'nin için C#.

## <a name="see-also"></a>Ayrıca bkz.

- [DUMPBIN Seçenekleri](../../build/reference/dumpbin-options.md)
