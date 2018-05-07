---
title: Birleştirme modüllerini kullanarak bileşenleri yeniden dağıtma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- merge modules, using
- redistributing applications, using merge modules
ms.assetid: 93b84211-bf9b-4a78-9f22-474ac2ef7840
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6d95b6d2a69b4b40c4464136dd33a8c5231185f5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="redistributing-components-by-using-merge-modules"></a>Birleştirme Modüllerini Kullanarak Bileşenleri Yeniden Dağıtma
Visual Studio içerir [birleştirme modülleri](http://msdn.microsoft.com/library/aa367434) uygulamayla yeniden dağıtılabilir için lisanslı her Visual C++ bileşeni için. Windows Installer kurulum dosyası içinde bir birleştirme modülü derlendiğinde, belirli DLL'lerin belirli bir platforma sahip bilgisayarlara dağıtımını sağlar. Kurulum dosyanızda, birleştirme modüllerinin uygulamanız için önkoşul olduğunu belirtin. Visual Studio yüklendiğinde, birleştirme modülleri \Program Files\Merge Modules yüklenen\\. (Yalnızca debug olmayan sürümleri Visual C++ DLL'leri yeniden dağıtılabilir.) Daha fazla bilgi ve dağıtım lisanslı birleştirme modülleri listesine bir bağlantı için bkz: [Visual C++ dosyalarını yeniden dağıtma](../ide/redistributing-visual-cpp-files.md).  
  
 Birleştirme modüllerini yeniden dağıtılabilir Visual C++ DLL'leri yükleme %SYSTEMROOT%\system32\ klasörüne etkinleştirmek için kullanabilirsiniz. (Visual Studio kendisini bu tekniği kullanır.) Bununla birlikte, yüklemeyi yapan kullanıcı yönetici haklarına sahip değilse, bu klasöre yükleme başarısız olur.  
  
 Uygulamanıza bakım yapmak zorunda olmadığınız ve DLL'lerin birden fazla sürümü üzerinde bağımlılıklarınızın bulunmadığı durumlar dışında, birleştirme modüllerini kullanmamanızı öneririz. Aynı DLL'nin farklı sürümlerine ilişkin birleştirme modülleri tek bir yükleyiciye dahil edilemez ve birleştirme modülleri, uygulamanızdan bağımsız olarak DLL'lerin bakımını yapmayı zorlaştırır. Bunun yerine, bir Visual C++ yeniden dağıtılabilir paketi yüklemenizi öneririz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual C++ Dosyalarını Yeniden Dağıtma](../ide/redistributing-visual-cpp-files.md)