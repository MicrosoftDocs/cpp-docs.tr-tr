---
title: ATL uygulamasını yeniden dağıtma
ms.date: 11/04/2016
helpviewer_keywords:
- ATL, redistributing
- redistributing ATL
- redistributing OLE DB templates
- OLE DB templates, redistributing
ms.assetid: 9a696b22-2345-43ec-826b-be7cb8cfd676
ms.openlocfilehash: a1da92a00d6bf88f41801f8eb99433d0c64812b1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62362419"
---
# <a name="redistributing-an-atl-application"></a>ATL uygulamasını yeniden dağıtma

Etkin Şablon kitaplığı (ATL) Visual Studio 2012'den itibaren bir yalnızca üstbilgi Kitaplığı'dır. ATL projeleri ATL seçeneği dinamik bir bağlantı yoktur. Yeniden dağıtılabilir hiçbir ATL kitaplığı gerekiyor.

ATL yürütülebilir bir uygulama dağıtırsanız, aşağıdaki komutu gönderdikten tarafından .exe dosyasını (ve içindeki tüm denetimleri) kaydetmeniz gerekir:

```
filename /regserver
```

Burada `filename` yürütülebilir dosya adıdır.

Visual Studio 2010'da bir ATL projesi MinDependency veya MinSize yapılandırması için oluşturulabilir. MinDependency yapılandırması ayarladığınızda aldığınızdır **kullanın, ATL** özelliğini **ATL'e Statik Bağlantı** üzerinde **genel** özellik sayfası ve kümesi  **Çalışma Zamanı Kitaplığı** özelliğini **çok iş parçacıklı (/ MT)** üzerinde **kod oluşturma** özellik sayfası (C/C++ klasörü).

Ayarladığınız tıkladığınızda bunları edinirsiniz bir MinSize yapılandırmadır **kullanın, ATL** özelliğini **ATL'e Dinamik bağlantı** üzerinde **genel** özellik sayfasında ya da kümesi **çalışma zamanı Kitaplık** özelliğini **çok iş parçacıklı DLL (/ MD)** üzerinde **kod oluşturma** özellik sayfası (C/C++ klasörü).

MinSize gerektiren ancak mümkün olduğunca küçük çıkış yapar ATL100.dll ve msvcr100.DLL'i tekrar (seçtiyseniz **çok iş parçacıklı DLL (/ MD)** seçeneği) hedef bilgisayardaki. ATL100.dll tüm ATL işlevleri mevcut olduğundan emin olmak için hedef bilgisayarda kayıtlı olmalıdır. ANSI ATL100.dll içerir ve Unicode aktarır.

ATL ya da OLE DB Şablonları projeniz MinDependency hedef için yapılandırdıysanız, daha büyük bir program görüntüsü alabilirsiniz olsa da, yüklemeniz ve hedef bilgisayarda ATL100.dll kaydetmeniz gerekmez.

ATL yürütülebilir bir uygulama dağıtırsanız, aşağıdaki komutu gönderdikten tarafından .exe dosyasını (ve içindeki tüm denetimleri) kaydetmeniz gerekir:

```
filename /regserver
```

Burada `filename` yürütülebilir dosya adıdır.

## <a name="see-also"></a>Ayrıca bkz.

[Visual C++ Dosyalarını Yeniden Dağıtma](redistributing-visual-cpp-files.md)
