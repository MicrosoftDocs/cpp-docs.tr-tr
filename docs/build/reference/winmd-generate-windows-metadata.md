---
title: /WINMD (Windows Meta Verileri Oluşturun)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.GenerateWindowsMetadata
ms.assetid: bcfb4901-411e-4c9e-9f78-23028b6e5fcc
ms.openlocfilehash: 93db20d14d3477734e35d33111246f9459310b90
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62317165"
---
# <a name="winmd-generate-windows-metadata"></a>/WINMD (Windows Meta Verileri Oluşturun)

Bir Windows çalışma zamanı meta veri (.winmd) dosyasının oluşturulmasını etkinleştirir.

> **/WINMD**\[**:**{**NO**\|**ONLY**}]

## <a name="arguments"></a>Arguments

**/WINMD**<br/>
Evrensel Windows platformu uygulamaları için varsayılan ayar. Bağlayıcı, ikili yürütülebilir dosyasının hem .winmd meta veri dosyası oluşturur.

**/WINMD:NO**<br/>
Bağlayıcı, yalnızca ikili yürütülebilir dosya, ancak bir .winmd dosyası oluşturur.

**/WINMD:ONLY**<br/>
Bağlayıcı, yalnızca .winmd dosyası, ancak değil ikili yürütülebilir dosya oluşturur.

## <a name="remarks"></a>Açıklamalar

**/WINMD** bağlayıcı seçeneği UWP uygulamaları ve Windows çalışma zamanı bileşenleri için bir Windows çalışma zamanı meta veri (.winmd) dosyası oluşturma denetlemek için kullanılır. .Winmd dosyası için Windows çalışma zamanı türlerini ve çalışma zamanı bileşenleri, uygulamaları bu türlerden birini söz konusu olduğunda meta verileri içeren DLL türüdür. Meta veriler aşağıdaki [ECMA-335](http://www.ecma-international.org/publications/standards/Ecma-335.htm) standart.

Varsayılan olarak, çıktı dosyası adını formundadır *binaryname*.winmd. Farklı bir dosya adı belirtmek için kullanın [/wınmdfıle](winmdfile-specify-winmd-file.md) seçeneği.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **bağlayıcı** > **Windows meta verileri** özellik sayfası.

1. İçinde **Windows meta verileri oluşturma** aşağı açılan liste kutusunda, kullanmak istediğiniz seçeneği seçin.

## <a name="see-also"></a>Ayrıca bkz.

[İzlenecek yol: Basit bir Windows çalışma zamanı bileşeni oluşturma ve JavaScript'ten çağırma](/windows/uwp/winrt-components/walkthrough-creating-a-simple-windows-runtime-component-and-calling-it-from-javascript)<br/>
[Microsoft arabirim tanım diline 3.0 giriş](/uwp/midl-3/intro)<br/>
[/WINMDFILE (winmd Dosyası Belirtin)](winmdfile-specify-winmd-file.md)<br/>
[/WINMDKEYFILE (winmd Anahtar Dosyası Belirtin)](winmdkeyfile-specify-winmd-key-file.md)<br/>
[/WINMDKEYCONTAINER (Tanımlayıcı Ad Anahtar Kapsayıcısı Belirtin)](winmdkeycontainer-specify-key-container.md)<br/>
[/WINMDDELAYSIGN (winmd Dosyasını Kısmen İmzalayın)](winmddelaysign-partially-sign-a-winmd.md)<br/>
[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC Bağlayıcı Seçenekleri](linker-options.md)
