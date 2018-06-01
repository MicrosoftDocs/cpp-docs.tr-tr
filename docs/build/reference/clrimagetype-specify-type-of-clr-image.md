---
title: / CLRIMAGETYPE (CLR görüntü türünü belirt) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /CLRIMAGETYPE
- VC.Project.VCLinkerTool.CLRImageType
dev_langs:
- C++
helpviewer_keywords:
- /CLRIMAGETYPE linker option
- -CLRIMAGETYPE linker option
ms.assetid: 04c60ee6-9dd7-4391-bc03-6926ad0fa116
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b5efb2e73e854591be7134753cec21a708fff3e5
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/01/2018
ms.locfileid: "34705016"
---
# <a name="clrimagetype-specify-type-of-clr-image"></a>/CLRIMAGETYPE (CLR Görüntü Türünü Belirt)

CLR görüntü türünü bağlantılı görüntüde ayarlayın.

## <a name="syntax"></a>Sözdizimi

> **/ CLRIMAGETYPE:**{**IJW**|**SAF**|**GÜVENLİ**|**SAFE32BITPREFERRED**}

## <a name="remarks"></a>Açıklamalar

Bağlayıcı yerel nesneleri kabul eder ve ayrıca kullanarak derlenen MSIL nesneleri [/CLR](../../build/reference/clr-common-language-runtime-compilation.md). **/CLR: pure** ve **/CLR: safe** derleyici seçenekleri Visual Studio 2015'te kullanım dışı bırakılan ve Visual Studio 2017 içinde desteklenmiyor. Karma nesneleri aynı derlemede geçirildiğinde, sonuçta elde edilen çıktı dosyası verifiability, varsayılan olarak, en düşük düzeyde verifiability giriş modüllerin eşit olur. Örneğin, yerel bir görüntü ve karma mod görüntü geçirirseniz (kullanarak derlenmiş **/CLR**), elde edilen görüntü bir karma mod görüntüsü olacaktır.

Kullanabileceğiniz **/CLRIMAGETYPE** bu ihtiyacınız olursa verifiability, daha düşük düzeyde belirtmek için.

Bir dosya CLR görüntü türünü belirleme hakkında daha fazla bilgi için bkz: [/CLRHEADER](../../build/reference/clrheader.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).

1. Genişletme **yapılandırma özellikleri** düğümü.

1. Genişletme **bağlayıcı** düğümü.

1. Seçin **Gelişmiş** özellik sayfası.

1. Değiştirme **CLR görüntü türünü** özelliği.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

1. Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.CLRImageType%2A>.

## <a name="see-also"></a>Ayrıca bkz.

- [Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)
- [Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)
