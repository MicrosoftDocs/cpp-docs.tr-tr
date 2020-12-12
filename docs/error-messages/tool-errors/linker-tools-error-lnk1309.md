---
description: 'Daha fazla bilgi edinin: bağlayıcı araçları hata LNK1309'
title: Bağlayıcı Araçları Hatası LNK1309
ms.date: 11/04/2016
f1_keywords:
- LNK1309
helpviewer_keywords:
- LNK1309
ms.assetid: 10146071-883f-4849-97d1-c7468f90efbb
ms.openlocfilehash: e04498ae5226f748b6ba5cc2ce0cd9340f4547c2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97193649"
---
# <a name="linker-tools-error-lnk1309"></a>Bağlayıcı Araçları Hatası LNK1309

> *Type1* modülü algılandı; /CLRIMAGETYPE:*type2* ile geçersiz

## <a name="remarks"></a>Açıklamalar

**/Clrimagetype** Ile bir clr görüntü türü istendi, ancak bir veya daha fazla modül bu türle uyumsuz olduğu için bağlayıcı bu türde bir görüntü üretemedi.

Örneğin, **/Clrimagetype: Safe** belirtirseniz ve **/clr: Pure** ile oluşturulmuş bir modül geçirirseniz LNK1309 görürsünüz.

**/Clr: Pure** ve **/clr: Safe** derleyici seçenekleri ve destek kitaplıkları Visual Studio 2015 ' de kullanımdan kaldırılmıştır ve Visual Studio 2017 ' de desteklenmez.

Ayrıca, Ptrustu [d]. lib kullanarak kısmen güvenilen bir CLR saf uygulaması oluşturmayı denerseniz da LNK1309 görürsünüz. Kısmen güvenilen bir uygulama oluşturma hakkında daha fazla bilgi için, bkz. [nasıl yapılır: CRT kitaplık DLL 'Inin bağımlılığını kaldırarak kısmen güvenilir uygulama oluşturma](../../dotnet/create-a-partially-trusted-application.md).

Daha fazla bilgi için bkz. [/clr (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md) ve [/Clrimagetype (clr görüntü türünü belirt)](../../build/reference/clrimagetype-specify-type-of-clr-image.md).
