---
title: Bağlayıcı araçları hatası LNK1309 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1309
dev_langs:
- C++
helpviewer_keywords:
- LNK1309
ms.assetid: 10146071-883f-4849-97d1-c7468f90efbb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0ffecdc891a9fe0d1c17d6e36c87f5df10b449ec
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/01/2018
ms.locfileid: "34704104"
---
# <a name="linker-tools-error-lnk1309"></a>Bağlayıcı Araçları Hatası LNK1309

> *type1* modülü algıladı; geçersiz geçiş /CLRIMAGETYPE:*type2*

## <a name="remarks"></a>Açıklamalar

Bir CLR görüntü türü ile istendi **/CLRIMAGETYPE** ancak bir veya daha fazla modül bu türüyle uyumlu olduğundan bağlayıcı türü görüntüsünü oluşturamadı.

Belirtirseniz, örneğin, LNK1309 göreceğiniz **/CLRIMAGETYPE:safe** ve ile yerleşik bir modül geçirdiğiniz **/CLR: pure**.

**/CLR: pure** ve **/CLR: safe** derleyici seçenekleri ve Destek kitaplıkları Visual Studio 2015'te kullanım dışı ve Visual Studio 2017 içinde desteklenmiyor.

Ptrustu [d] .lib kullanarak kısmen güvenilen bir CLR saf uygulaması oluşturma çalışırsanız, ayrıca LNK1309 görürsünüz. Kısmen güvenilir uygulama oluşturma hakkında daha fazla bilgi için bkz: [nasıl yapılır: CRT kitaplık DLL bağımlılık kaldırma tarafından bir kısmen güvenilir uygulama oluşturma](../../dotnet/create-a-partially-trusted-application.md).

Daha fazla bilgi için bkz: [/CLR (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md) ve [/CLRIMAGETYPE (belirtin, CLR Resim türünde)](../../build/reference/clrimagetype-specify-type-of-clr-image.md).