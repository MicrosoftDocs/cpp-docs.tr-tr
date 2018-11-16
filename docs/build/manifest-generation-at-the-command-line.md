---
title: Komut Satırında Bildirim Üretme
ms.date: 11/04/2016
helpviewer_keywords:
- manifests [C++]
- manifest tool (mt.exe)
ms.assetid: fc2ff255-82b1-4c44-af76-8405c5850292
ms.openlocfilehash: 440bf785f61a438099a394319a6df6e7389a608d
ms.sourcegitcommit: b032daf81cb5fdb1f5a988277ee30201441c4945
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2018
ms.locfileid: "51692534"
---
# <a name="manifest-generation-at-the-command-line"></a>Komut Satırında Bildirim Üretme

Bağlayıcı işlenen tüm nesne dosyaları ve son ikili yerleşik sonra nmake veya benzer araçlarını kullanarak komut satırından C/C++ uygulamaları oluştururken, bildirim oluşturulur. Bağlayıcı, nesne dosyalarında depolanan derleme bilgilerini toplar ve son bir bildirim dosyasına bu bilgileri bir araya getirir. Varsayılan olarak bağlayıcı adlı bir dosya oluşturur *binary_name*. *Uzantı*.manifest son ikili tanımlamak için. Bağlayıcı, ikili dosya içinde bir bildirim dosyası ekleme değil ve yalnızca bir dış dosya olarak bir bildirimde oluşturabilir. Son ikili kullanma gibi bildirim katıştırma için çeşitli yollar vardır [bildirim Aracı (mt.exe)](https://msdn.microsoft.com/library/aa375649) veya bir kaynak dosyasına bildirim derleniyor. Oturum, son ikili olarak artımlı bağlamayı, gibi özellikleri etkinleştirmek için bildirim eklerken izlenmesi için belirli kurallar sahip göz önünde bulundurun ve Düzenle ve devam etmek önemlidir. Bunlar ve diğer seçenekleri ele alınmıştır [nasıl yapılır: bir bildirim içinde bir C/C++ uygulamasına ekleme](../build/how-to-embed-a-manifest-inside-a-c-cpp-application.md) komut satırında oluştururken.

## <a name="see-also"></a>Ayrıca Bkz.

[Bildirimleri](/windows/desktop/sbscs/manifests)<br/>
[/INCREMENTAL (Artımlı Bağla)](../build/reference/incremental-link-incrementally.md)<br/>
[Tanımlayıcı Ad Derlemeleri (Derleme İmzalama) (C++/CLI)](../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md)<br/>
[Düzenle ve Devam Et](/visualstudio/debugger/edit-and-continue)<br/>
[C/C++ Programları Bildirim Üretimini Anlama](../build/understanding-manifest-generation-for-c-cpp-programs.md)<br/>
