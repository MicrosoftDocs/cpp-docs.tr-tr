---
description: 'Daha fazla bilgi edinin: ATL uygulamasını yeniden dağıtma'
title: ATL uygulamasını yeniden dağıtma
ms.date: 11/04/2016
helpviewer_keywords:
- ATL, redistributing
- redistributing ATL
- redistributing OLE DB templates
- OLE DB templates, redistributing
ms.assetid: 9a696b22-2345-43ec-826b-be7cb8cfd676
ms.openlocfilehash: 58021416eb7f258e1d436ff099ebf9c647dfc0bc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97179960"
---
# <a name="redistributing-an-atl-application"></a>ATL uygulamasını yeniden dağıtma

Visual Studio 2012 ' den başlayarak, etkin şablon kitaplığı (ATL) yalnızca üst bilgi kitaplığı olur. ATL projelerinin ATL seçeneğine dinamik bağlantısı yoktur. Yeniden dağıtılabilir ATL Kitaplığı gerekli değildir.

ATL yürütülebilir uygulamasını yeniden dağıtırsanız, aşağıdaki komutu vererek. exe dosyasını (ve içindeki tüm denetimleri) kaydetmeniz gerekir:

```
filename /regserver
```

, `filename` yürütülebilir dosyanın adıdır.

Visual Studio 2010 ' de, bir ATL projesi MinDependency veya MinSize yapılandırması için oluşturulabilir. MinDependency yapılandırması, **ATL** özelliğinin **genel** Özellik sayfasında **ATL 'ye statik bağlantı** olarak ayarlandığı ve **çalışma zamanı kitaplığı** özelliğini **kod oluşturma** Özellik sayfasında (C/C++ klasörü) **Çoklu iş parçacıklı (/MT)** olarak ayarladığınızda alacağınız şeydir.

MinSize yapılandırması, **ATL** özelliğinin **genel** Özellik sayfasında **ATL 'e dinamik bağlantı** olarak ayarlandığı veya **çalışma zamanı kitaplığı** özelliğini **kod oluşturma** Özellik SAYFASıNDA (C/C++ klasörü) **Çoklu iş parçacıklı DLL (/MD)** olarak ayarlamanız durumunda alacağınız şeydir.

MinSize, çıkış dosyasını mümkün olduğunca küçük yapar, ancak ATL100.dll ve Msvcr100.dll gerektirir ( **çok iş PARÇACıKLı dll (/MD)** seçeneğini belirlediyseniz) hedef bilgisayarda bulunur. Tüm ATL işlevlerinin mevcut olduğundan emin olmak için hedef bilgisayara ATL100.dll kaydedilmelidir. ATL100.dll ANSI ve Unicode dışarı aktarmaları içerir.

Bir MinDependency hedefi için ATL veya OLE DB şablonları projenizi derliyorsanız, daha büyük bir program görüntüsü almanıza rağmen hedef bilgisayara ATL100.dll yüklemeniz ve kaydetmeniz gerekmez.

ATL yürütülebilir uygulamasını yeniden dağıtırsanız, aşağıdaki komutu vererek. exe dosyasını (ve içindeki tüm denetimleri) kaydetmeniz gerekir:

```
filename /regserver
```

, `filename` yürütülebilir dosyanın adıdır.

## <a name="see-also"></a>Ayrıca bkz.

[Visual C++ Dosyalarını Yeniden Dağıtma](redistributing-visual-cpp-files.md)
