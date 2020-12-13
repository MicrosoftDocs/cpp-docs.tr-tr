---
description: Şu konuda daha fazla bilgi edinin:/CLRHEADER
title: /CLRHEADER
ms.date: 05/16/2019
f1_keywords:
- /CLRHEADER
helpviewer_keywords:
- -CLRHEADER dumpbin option
- /CLRHEADER dumpbin option
- CLRHEADER dumpbin option
ms.assetid: cf73424f-4541-47e2-b94e-69b95266ef2a
ms.openlocfilehash: 8866707ae629672c3ae9ebb468d145eafb0475c4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97182430"
---
# <a name="clrheader"></a>/CLRHEADER

CLR 'ye özgü bilgileri görüntüleyin.

## <a name="syntax"></a>Syntax

> /CLRHEADER *dosyası*

### <a name="arguments"></a>Arguments

*dosyasýný*<br/>
[/Clr](clr-common-language-runtime-compilation.md)ile oluşturulmuş bir görüntü dosyası.

## <a name="remarks"></a>Açıklamalar

**/CLRHEADER** herhangi bir yönetilen programda kullanılan .net üstbilgileri hakkındaki bilgileri görüntüler. Çıktı, .NET üstbilgisinin ve üstbilgideki bölümlerin konumunu ve boyutunu bayt cinsinden gösterir.

[/GL](gl-whole-program-optimization.md) derleyici seçeneği ile oluşturulan dosyalarda yalnızca [/Headers](headers.md) dumpbin seçeneği kullanılabilir.

/Clr ile derlenen bir dosyada **/CLRHEADER** kullanıldığında, dumpbin çıkışında bir **clr üst bilgisi:** bölümü olur. **Bayrakların** değeri hangi/CLR seçeneğinin kullanıldığını gösterir:

- 0--/clr (görüntü yerel kod içeriyor olabilir).

Ayrıca, ortak dil çalışma zamanı için bir görüntünün oluşturulup oluşturulmayacağı programlı bir şekilde denetleyebilirsiniz.  Daha fazla bilgi için bkz. [nasıl yapılır: bir resmin yerel mi yoksa clr mi olduğunu belirleme](../../dotnet/how-to-determine-if-an-image-is-native-or-clr.md).

**/Clr: Pure** ve **/clr: Safe** derleyici seçenekleri Visual Studio 2015 ' de kullanımdan kaldırılmıştır ve Visual Studio 2017 ve sonrasında desteklenmez. "Saf" veya "güvenli" olması gereken kod C# ' ye eklenmelidir.

## <a name="see-also"></a>Ayrıca bkz.

- [DUMPBIN Seçenekleri](dumpbin-options.md)
