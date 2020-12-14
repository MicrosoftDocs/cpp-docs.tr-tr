---
description: Daha fazla bilgi edinin:/WINMD (Windows meta verileri oluştur)
title: /WINMD (Windows Meta Verileri Oluşturun)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.GenerateWindowsMetadata
ms.assetid: bcfb4901-411e-4c9e-9f78-23028b6e5fcc
ms.openlocfilehash: 7cf52a49716e6ec30a29c7e6a96fe7a078b4830c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97259090"
---
# <a name="winmd-generate-windows-metadata"></a>/WINMD (Windows Meta Verileri Oluşturun)

Windows Çalışma Zamanı meta veri (. winmd) dosyasının oluşturulmasını mümkün.

> **/Winmd** \[ **:**{ \| **yalnızca** Hayır}]

## <a name="arguments"></a>Arguments

**/WıNMD**<br/>
Evrensel Windows Platformu uygulamalar için varsayılan ayar. Bağlayıcı hem ikili yürütülebilir dosyayı hem de. winmd meta veri dosyasını üretir.

**/WINMD: HAYıR**<br/>
Bağlayıcı, bir. winmd dosyası değil yalnızca ikili yürütülebilir dosyayı oluşturur.

**/WINMD: YALNıZCA**<br/>
Bağlayıcı yalnızca. winmd dosyasını oluşturur, ikili yürütülebilir dosyayı değil.

## <a name="remarks"></a>Açıklamalar

**/Winmd** bağlayıcı SEÇENEĞI, UWP uygulamaları ve Windows çalışma zamanı bileşenleri için bir Windows çalışma zamanı meta veri (. WINMD) dosyası oluşturulmasını denetlemek için kullanılır. Bir. winmd dosyası, Windows çalışma zamanı türleri için meta veriler içeren ve çalışma zamanı bileşenleri durumunda bu türlerin uygulamaları içeren bir DLL türüdür. Meta veriler [ECMA-335](https://www.ecma-international.org/publications/standards/Ecma-335.htm) standardını izler.

Varsayılan olarak, çıkış dosyası adının *binaryname*. winmd biçimi vardır. Farklı bir dosya adı belirtmek için [/WinMDFile](winmdfile-specify-winmd-file.md) seçeneğini kullanın.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **bağlayıcı**  >  **Windows meta verileri** özellik sayfasını seçin.

1. **Windows meta verileri oluştur** aşağı açılan liste kutusunda istediğiniz seçeneği belirleyin.

## <a name="see-also"></a>Ayrıca bkz.

[İzlenecek yol: basit bir Windows Çalışma Zamanı bileşeni oluşturma ve JavaScript 'ten çağırma](/windows/uwp/winrt-components/walkthrough-creating-a-simple-windows-runtime-component-and-calling-it-from-javascript)<br/>
[Microsoft Arabirim Tanımlama Dili 3,0 'ye giriş](/uwp/midl-3/intro)<br/>
[/WINMDFILE (WinMD dosyası belirtin)](winmdfile-specify-winmd-file.md)<br/>
[/WINMDKEYFILE (WinMD anahtar dosyası belirtin)](winmdkeyfile-specify-winmd-key-file.md)<br/>
[/WINMDKEYCONTAINER (anahtar kapsayıcısını belirt)](winmdkeycontainer-specify-key-container.md)<br/>
[/WINMDDELAYSIGN (bir WinMD 'yi kısmen Imzala)](winmddelaysign-partially-sign-a-winmd.md)<br/>
[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)
