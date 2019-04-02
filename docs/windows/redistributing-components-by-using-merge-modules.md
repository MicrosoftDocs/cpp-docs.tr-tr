---
title: Birleştirme Modüllerini Kullanarak Bileşenleri Yeniden Dağıtma
ms.date: 11/04/2016
helpviewer_keywords:
- merge modules, using
- redistributing applications, using merge modules
ms.assetid: 93b84211-bf9b-4a78-9f22-474ac2ef7840
ms.openlocfilehash: 7a110826e21f33986d68dcd46417ec5cbd5171bc
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58787882"
---
# <a name="redistributing-components-by-using-merge-modules"></a>Birleştirme Modüllerini Kullanarak Bileşenleri Yeniden Dağıtma

Visual Studio içerir [birleştirme modülleri](/windows/desktop/Msi/about-merge-modules) uygulamayla dağıtılmak üzere lisanslı her Visual C++ bileşeni. Windows Installer kurulum dosyası içinde bir birleştirme modülü derlendiğinde, belirli DLL'lerin belirli bir platforma sahip bilgisayarlara dağıtımını sağlar. Kurulum dosyanızda, birleştirme modüllerinin uygulamanız için önkoşul olduğunu belirtin. Visual Studio yüklendiğinde, birleştirme modülleri Files\Merge modülleri \Program içinde yüklenen\\. (Yalnızca hata ayıklamasız sürümleri Visual C++ DLL'lerini yeniden dağıtılabilir.) Daha fazla bilgi ve yeniden dağıtım için lisanslı birleştirme modülleri listesini bağlantısını için bkz: [Visual C++ dosyalarını yeniden dağıtma](redistributing-visual-cpp-files.md).

Yeniden dağıtılabilir Visual C++ DLL'lerinin %SYSTEMROOT%\system32\ klasörüne yüklenmesini etkinleştirmek için birleştirme modüllerini kullanabilirsiniz. (Visual Studio kendisi bu tekniği kullanır.) Bununla birlikte, yüklemeyi yapan kullanıcı yönetici haklarına sahip değilse, bu klasöre yükleme başarısız olur.

Uygulamanıza bakım yapmak zorunda olmadığınız ve DLL'lerin birden fazla sürümü üzerinde bağımlılıklarınızın bulunmadığı durumlar dışında, birleştirme modüllerini kullanmamanızı öneririz. Aynı DLL'nin farklı sürümlerine ilişkin birleştirme modülleri tek bir yükleyiciye dahil edilemez ve birleştirme modülleri, uygulamanızdan bağımsız olarak DLL'lerin bakımını yapmayı zorlaştırır. Bunun yerine, bir Visual C++ yeniden dağıtılabilir paketi yüklemenizi öneririz.

## <a name="see-also"></a>Ayrıca bkz.

[Visual C++ Dosyalarını Yeniden Dağıtma](redistributing-visual-cpp-files.md)