---
title: Birleştirme Modüllerini Kullanarak Bileşenleri Yeniden Dağıtma
ms.date: 11/04/2016
helpviewer_keywords:
- merge modules, using
- redistributing applications, using merge modules
ms.assetid: 93b84211-bf9b-4a78-9f22-474ac2ef7840
ms.openlocfilehash: 36dc115987b051f117264991927c2599a88deda6
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69514765"
---
# <a name="redistributing-components-by-using-merge-modules"></a>Birleştirme Modüllerini Kullanarak Bileşenleri Yeniden Dağıtma

Visual Studio, bir uygulamayla yeniden dağıtılması lisanslanan her görsel C++ bileşen için [birleştirme modüllerini](/windows/win32/Msi/about-merge-modules) içerir. Windows Installer kurulum dosyası içinde bir birleştirme modülü derlendiğinde, belirli DLL'lerin belirli bir platforma sahip bilgisayarlara dağıtımını sağlar. Kurulum dosyanızda, birleştirme modüllerinin uygulamanız için önkoşul olduğunu belirtin. Visual Studio yüklendiğinde, birleştirme modülleri \Program Files\Common Files\Merge modüllerine\\yüklenir. (Yalnızca Visual C++ dll 'lerin hata ayıklama olmayan sürümleri yeniden dağıtılabilir.) Daha fazla bilgi ve yeniden dağıtım için lisanslanan birleştirme modülleri listesinin bir bağlantısı için bkz. [ C++ görsel dosyaları yeniden dağıtma](redistributing-visual-cpp-files.md).

Yeniden dağıtılabilir Visual C++ dll 'leri%SystemRoot%\system32\ klasörüne yüklemeyi etkinleştirmek için birleştirme modüllerini kullanabilirsiniz. (Visual Studio 'Nun kendisi bu tekniği kullanır.) Bununla birlikte, yüklemeyi yapan kullanıcı yönetici haklarına sahip değilse, bu klasöre yükleme başarısız olur.

Uygulamanıza bakım yapmak zorunda olmadığınız ve DLL'lerin birden fazla sürümü üzerinde bağımlılıklarınızın bulunmadığı durumlar dışında, birleştirme modüllerini kullanmamanızı öneririz. Aynı DLL'nin farklı sürümlerine ilişkin birleştirme modülleri tek bir yükleyiciye dahil edilemez ve birleştirme modülleri, uygulamanızdan bağımsız olarak DLL'lerin bakımını yapmayı zorlaştırır. Bunun yerine, bir görsel C++ yeniden dağıtılabilir paket yüklemenizi öneririz.

## <a name="see-also"></a>Ayrıca bkz.

[Visual C++ Dosyalarını Yeniden Dağıtma](redistributing-visual-cpp-files.md)
