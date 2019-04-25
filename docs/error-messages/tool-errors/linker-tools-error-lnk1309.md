---
title: Bağlayıcı Araçları Hatası LNK1309
ms.date: 11/04/2016
f1_keywords:
- LNK1309
helpviewer_keywords:
- LNK1309
ms.assetid: 10146071-883f-4849-97d1-c7468f90efbb
ms.openlocfilehash: ea675ca835dfc3fe4881e5fabbea746a4442b10a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62187449"
---
# <a name="linker-tools-error-lnk1309"></a>Bağlayıcı Araçları Hatası LNK1309

> *type1* modülü algılandı; geçersiz geçiş/CLRIMAGETYPE:*type2*

## <a name="remarks"></a>Açıklamalar

CLR imaj türü ile istendi **/CLRIMAGETYPE** ancak bir veya daha fazla modül bu türü ile uyumlu değil çünkü bağlayıcı türü görüntüsü oluşturamadı.

Örneğin belirtirseniz LNK1309 görürsünüz **kullanılır** ve ile oluşturulmuş bir modül geçirdiğiniz **/CLR: pure**.

**/CLR: pure** ve **/CLR: safe** derleyici seçenekleri ve Destek kitaplıkları Visual Studio 2015'te kullanım dışı ve Visual Studio 2017'de desteklenmiyor.

[D] ptrustu .lib kullanarak kısmen güvenilen bir CLR saf uygulama oluşturmaya çalışırsanız, LNK1309 görürsünüz. Kısmen güvenilir uygulama oluşturma hakkında daha fazla bilgi için bkz: [nasıl yapılır: CRT kitaplık DLL'İNDEN bağımlılık kaldırarak kısmen güvenilir uygulama oluşturma](../../dotnet/create-a-partially-trusted-application.md).

Daha fazla bilgi için [/CLR (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md) ve [/CLRIMAGETYPE (CLR, türü görüntü belirtin)](../../build/reference/clrimagetype-specify-type-of-clr-image.md).