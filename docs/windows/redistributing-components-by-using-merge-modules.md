---
description: 'Daha fazla bilgi edinin: birleştirme modüllerini kullanarak bileşenleri yeniden dağıtma'
title: Birleştirme Modüllerini Kullanarak Bileşenleri Yeniden Dağıtma
ms.date: 11/04/2016
helpviewer_keywords:
- merge modules, using
- redistributing applications, using merge modules
ms.assetid: 93b84211-bf9b-4a78-9f22-474ac2ef7840
ms.openlocfilehash: ecfc2904be7451c96226e91ed8e7f98d565d35ac
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97179908"
---
# <a name="redistributing-components-by-using-merge-modules"></a>Birleştirme Modüllerini Kullanarak Bileşenleri Yeniden Dağıtma

Visual Studio, bir uygulamayla yeniden dağıtılması lisanslanan her bir Visual C++ bileşeni için [birleştirme modüllerini](/windows/win32/Msi/about-merge-modules) içerir. Windows Installer kurulum dosyası içinde bir birleştirme modülü derlendiğinde, belirli DLL'lerin belirli bir platforma sahip bilgisayarlara dağıtımını sağlar. Kurulum dosyanızda, birleştirme modüllerinin uygulamanız için önkoşul olduğunu belirtin. Visual Studio yüklendiğinde, birleştirme modülleri \Program Files\Common Files\Merge modüllerine yüklenir \\ . (Yalnızca Visual C++ dll 'lerin hata ayıklamasız sürümleri yeniden dağıtılabilir.) Daha fazla bilgi ve yeniden dağıtım için lisanslanan bir birleştirme modülleri listesi bağlantısı için bkz. [Visual C++ dosyalarını yeniden dağıtma](redistributing-visual-cpp-files.md).

Yeniden dağıtılabilir Visual C++ dll 'Leri%SYSTEMROOT%\system32\ klasörüne yüklemeyi etkinleştirmek için birleştirme modüllerini kullanabilirsiniz. (Visual Studio 'Nun kendisi bu tekniği kullanır.) Ancak, yükleme kullanıcısı yönetici haklarına sahip olmadığı takdirde bu klasöre yükleme başarısız olur.

Uygulamanıza bakım yapmak zorunda olmadığınız ve DLL'lerin birden fazla sürümü üzerinde bağımlılıklarınızın bulunmadığı durumlar dışında, birleştirme modüllerini kullanmamanızı öneririz. Aynı DLL'nin farklı sürümlerine ilişkin birleştirme modülleri tek bir yükleyiciye dahil edilemez ve birleştirme modülleri, uygulamanızdan bağımsız olarak DLL'lerin bakımını yapmayı zorlaştırır. Bunun yerine, Visual C++ yeniden dağıtılabilir bir paket yüklemenizi öneririz.

## <a name="see-also"></a>Ayrıca bkz.

[Visual C++ Dosyalarını Yeniden Dağıtma](redistributing-visual-cpp-files.md)
