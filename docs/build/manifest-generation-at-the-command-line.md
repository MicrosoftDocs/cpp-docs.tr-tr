---
description: Hakkında daha fazla bilgi için bkz. komut satırında bildirim oluşturma
title: Komut Satırında Bildirim Üretme
ms.date: 11/04/2016
helpviewer_keywords:
- manifests [C++]
- manifest tool (mt.exe)
ms.assetid: fc2ff255-82b1-4c44-af76-8405c5850292
ms.openlocfilehash: 30b826e0fe98a143f58d7987203881a8fd8e601b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97176463"
---
# <a name="manifest-generation-at-the-command-line"></a>Komut Satırında Bildirim Üretme

Komut satırından NMAKE veya benzer araçları kullanarak C/C++ uygulamaları oluştururken bildirim, bağlayıcı tüm nesne dosyalarını işledikten ve son ikiliyi derlendikten sonra oluşturulur. Bağlayıcı, nesne dosyalarında depolanan derleme bilgilerini toplar ve bu bilgileri son bildirim dosyasında birleştirir. Varsayılan olarak, bağlayıcı *binary_name* adlı bir dosya oluşturur. Son ikiliyi betimleyen *. manifest.* Bağlayıcı, ikili dosya içine bir bildirim dosyası eklemez ve yalnızca bir bildirimi dış dosya olarak oluşturabilir. Bildirim [aracını (mt.exe)](/windows/win32/sbscs/mt-exe) kullanma veya bildirimi bir kaynak dosyasında derleme gibi son ikiliye eklemek için birkaç yol vardır. Bu tür özellikleri artımlı bağlama, imzalama ve düzenleme ve devam etme olarak etkinleştirmek için son ikiliye bir bildirim Katıştırırken belirli kuralların izlenmesini göz önünde bulundurmanız önemlidir. Bu ve diğer seçenekler, komut satırında derlerken [bir C/C++ uygulamasının Içine bildirim ekleme konusunda](how-to-embed-a-manifest-inside-a-c-cpp-application.md) ele alınmıştır.

## <a name="see-also"></a>Ayrıca bkz.

[Listeleri](/windows/win32/sbscs/manifests)<br/>
[/Artımlı (artımlı bağlantı)](reference/incremental-link-incrementally.md)<br/>
[Tanımlayıcı Ad Derlemeleri (Derleme İmzalama) (C++/CLI)](../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md)<br/>
[Düzenle ve Devam Et](/visualstudio/debugger/edit-and-continue)<br/>
[C/C++ programları için bildirim oluşturmayı anlama](understanding-manifest-generation-for-c-cpp-programs.md)<br/>
