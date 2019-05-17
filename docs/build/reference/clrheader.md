---
title: /CLRHEADER
ms.date: 05/16/2019
f1_keywords:
- /CLRHEADER
helpviewer_keywords:
- -CLRHEADER dumpbin option
- /CLRHEADER dumpbin option
- CLRHEADER dumpbin option
ms.assetid: cf73424f-4541-47e2-b94e-69b95266ef2a
ms.openlocfilehash: 5974606448dad103c8f12a126b8d17c688927c88
ms.sourcegitcommit: a10c9390413978d36b8096b684d5ed4cf1553bc8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/17/2019
ms.locfileid: "65837160"
---
# <a name="clrheader"></a>/CLRHEADER

CLR özel bilgileri görüntüler.

## <a name="syntax"></a>Sözdizimi

> / CLRHEADER *dosyası*

### <a name="arguments"></a>Arguments

*Dosya*<br/>
Bir resim dosyası ile oluşturulmuş [/CLR](clr-common-language-runtime-compilation.md).

## <a name="remarks"></a>Açıklamalar

**/ CLRHEADER** herhangi bir yönetilen programında kullanılan .NET üst bilgileri hakkındaki bilgileri görüntüler. Çıktı, .NET üstbilgi ve bölümleri üst bilgisindeki bayt cinsinden boyutunu ve konumunu gösterir.

Yalnızca [OPTIONAL](headers.md) DUMPBIN seçeneği ile üretilen dosyalar kullanıma [/GL](gl-whole-program-optimization.md) derleyici seçeneği.

Zaman **/CLRHEADER** kullanılan/CLR ile derlenen bir dosyada olacaktır bir **clr üst bilgi:** dumpbin çıkış bölümünde. Değerini **bayrakları** hangi/CLR seçeneği kullanılan gösterir:

- 0 – / CLR (yerel kod görüntü içerebilir).

Görüntüyü bir ortak dil çalışma zamanı için oluşturulmuş programlama yoluyla da kontrol edebilirsiniz.  Daha fazla bilgi için [nasıl yapılır: Görüntüyü yerel mi yoksa CLR mi belirlemek](../../dotnet/how-to-determine-if-an-image-is-native-or-clr.md).

**/CLR: pure** ve **/CLR: safe** derleyici seçenekleri Visual Studio 2015'te kullanım dışı ve Visual Studio 2017 ve sonraki sürümlerde desteklenmiyor. "Saf" veya "güvenli" olmalıdır kod unity'nin için C#.

## <a name="see-also"></a>Ayrıca bkz.

- [DUMPBIN Seçenekleri](dumpbin-options.md)
