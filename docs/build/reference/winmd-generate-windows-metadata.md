---
title: -WINMD (Windows meta verileri oluşturun) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.GenerateWindowsMetadata
dev_langs:
- C++
ms.assetid: bcfb4901-411e-4c9e-9f78-23028b6e5fcc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 492be2c5510155ab0336070adc4b5ae96a9775c0
ms.sourcegitcommit: 8480f16893f09911f08a58caf684405404f7ac8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49162964"
---
# <a name="winmd-generate-windows-metadata"></a>/WINMD (Windows Meta Verileri Oluşturun)

Bir Windows çalışma zamanı meta veri (.winmd) dosyasının oluşturulmasını etkinleştirir.

> **/ WINMD**\[**:**{**HAYIR**\|**YALNIZCA**}]

## <a name="arguments"></a>Arguments

**/ WINMD**<br/>
Evrensel Windows platformu uygulamaları için varsayılan ayar. Bağlayıcı, ikili yürütülebilir dosyasının hem .winmd meta veri dosyası oluşturur.

**/WINMD:NO**<br/>
Bağlayıcı, yalnızca ikili yürütülebilir dosya, ancak bir .winmd dosyası oluşturur.

**/ WINMD: YALNIZCA**<br/>
Bağlayıcı, yalnızca .winmd dosyası, ancak değil ikili yürütülebilir dosya oluşturur.

## <a name="remarks"></a>Açıklamalar

**/WINMD** bağlayıcı seçeneği UWP uygulamaları ve Windows çalışma zamanı bileşenleri için bir Windows çalışma zamanı meta veri (.winmd) dosyası oluşturma denetlemek için kullanılır. .Winmd dosyası için Windows çalışma zamanı türlerini ve çalışma zamanı bileşenleri, uygulamaları bu türlerden birini söz konusu olduğunda meta verileri içeren DLL türüdür. Meta veriler aşağıdaki [ECMA-335](http://www.ecma-international.org/publications/standards/Ecma-335.htm) standart.

Varsayılan olarak, çıktı dosyası adını formundadır *binaryname*.winmd. Farklı bir dosya adı belirtmek için kullanın [/wınmdfıle](../../build/reference/winmdfile-specify-winmd-file.md) seçeneği.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **bağlayıcı** > **Windows meta verileri** özellik sayfası.

1. İçinde **Windows meta verileri oluşturma** aşağı açılan liste kutusunda, kullanmak istediğiniz seçeneği seçin.

## <a name="see-also"></a>Ayrıca Bkz.

[İzlenecek yol: basit bir Windows çalışma zamanı bileşeni oluşturma ve JavaScript'ten çağırma](/windows/uwp/winrt-components/walkthrough-creating-a-simple-windows-runtime-component-and-calling-it-from-javascript)<br/>
[Microsoft arabirim tanım diline 3.0 giriş](/uwp/midl-3/intro)<br/>
[/WINMDFILE (winmd Dosyası Belirtin)](winmdfile-specify-winmd-file.md)<br/>
[/WINMDKEYFILE (winmd Anahtar Dosyası Belirtin)](winmdkeyfile-specify-winmd-key-file.md)<br/>
[/WINMDKEYCONTAINER (Tanımlayıcı Ad Anahtar Kapsayıcısı Belirtin)](winmdkeycontainer-specify-key-container.md)<br/>
[/WINMDDELAYSIGN (winmd Dosyasını Kısmen İmzalayın)](winmddelaysign-partially-sign-a-winmd.md)<br/>
[Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)<br/>
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)
