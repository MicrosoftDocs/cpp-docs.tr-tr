---
title: Komut Satırında Bildirim Üretme
ms.date: 11/04/2016
helpviewer_keywords:
- manifests [C++]
- manifest tool (mt.exe)
ms.assetid: fc2ff255-82b1-4c44-af76-8405c5850292
ms.openlocfilehash: 381406213422e286dd9aba26adcdbd6caff7bfe3
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69493199"
---
# <a name="manifest-generation-at-the-command-line"></a>Komut Satırında Bildirim Üretme

Komut satırından NMAKEC++ veya benzer araçları kullanarak C/uygulamaları derlerken, bildirim bağlayıcı tüm nesne dosyalarını işledikten ve son ikiliyi derlendikten sonra oluşturulur. Bağlayıcı, nesne dosyalarında depolanan derleme bilgilerini toplar ve bu bilgileri son bildirim dosyasında birleştirir. Varsayılan olarak, bağlayıcı *binary_name*adlı bir dosya oluşturur.son ikiliyi betimleyen. manifest. Bağlayıcı, ikili dosya içine bir bildirim dosyası eklemez ve yalnızca bir bildirimi dış dosya olarak oluşturabilir. Bildirim [aracını (MT. exe)](/windows/win32/sbscs/mt-exe) kullanma veya bildirimi bir kaynak dosyasında derleme gibi son ikiliye eklemek için birkaç yol vardır. Bu tür özellikleri artımlı bağlama, imzalama ve düzenleme ve devam etme olarak etkinleştirmek için son ikiliye bir bildirim Katıştırırken belirli kuralların izlenmesini göz önünde bulundurmanız önemlidir. Bu ve diğer seçenekler şu şekilde açıklanmıştır [: Komut satırını oluştururken bir C/C++ uygulamasının](how-to-embed-a-manifest-inside-a-c-cpp-application.md) içine bildirim ekleyin.

## <a name="see-also"></a>Ayrıca bkz.

[Listeleri](/windows/win32/sbscs/manifests)<br/>
[/INCREMENTAL (Artımlı Bağla)](reference/incremental-link-incrementally.md)<br/>
[Tanımlayıcı Ad Derlemeleri (Derleme İmzalama) (C++/CLI)](../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md)<br/>
[Düzenle ve Devam Et](/visualstudio/debugger/edit-and-continue)<br/>
[C/C++ Programları Bildirim Üretimini Anlama](understanding-manifest-generation-for-c-cpp-programs.md)<br/>
