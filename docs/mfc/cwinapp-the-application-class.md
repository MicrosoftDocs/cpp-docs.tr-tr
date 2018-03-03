---
title: "CWinApp: Uygulama sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CWinApp
dev_langs:
- C++
helpviewer_keywords:
- application class [MFC]
- CWinApp class [MFC], CWinThread
- MFC, WinMain and
- CWinApp class [MFC], multithreading
- CWinThread class [MFC], and CWinApp
- InitApplication method [MFC]
- WinMain method [MFC]
- WinMain method [MFC], in MFC
- CWinApp class [MFC], WinMain
ms.assetid: 935822bb-d463-481b-a5f6-9719d68ed1d5
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c1f146df2dd4f97affdaf1c3107d1b00bfd86876
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cwinapp-the-application-class"></a>CWinApp: Uygulama Sınıfı
MFC ana uygulama sınıfında başlatma, çalışan ve Windows işletim sistemi için uygulama sonlandırılması yalıtır. Bir çerçevede bir uygulama olmalıdır ve yalnızca bir nesne sınıfının türetilen [CWinApp](../mfc/reference/cwinapp-class.md). Bu nesne Windows oluşturulmadan önce oluşturulur.  
  
 `CWinApp`türetilmiş `CWinThread`, bir veya daha fazla iş parçacığı olabilir, uygulamanız için yürütme ana iş parçacığının temsil eder. MFC, son sürümlerinde `InitInstance`, **çalıştırmak**, `ExitInstance`, ve `OnIdle` üye işlevleri olan gerçekte sınıfında `CWinThread`. Bu işlevler oldukları gibi burada açıklanan `CWinApp` üyeleri bunun yerine, tartışma nesnenin rol uygulama nesnesi olarak yerine birincil iş parçacığı olarak işlemiyle ilgili olduğundan.  
  
> [!NOTE]
>  Uygulama sınıfınızda, uygulamanızın birincil iş parçacığı yürütme meydana gelir. Win32 API işlevleri kullanarak, yürütme İkincil iş parçacıklarının de oluşturabilirsiniz. Bu iş parçacıkları MFC kitaplığını kullanabilirsiniz. Daha fazla bilgi için bkz: [çoklu iş parçacığı kullanımı](../parallel/multithreading-support-for-older-code-visual-cpp.md).  
  
 Windows işletim sistemi için herhangi bir program gibi framework uygulamanız sahip bir `WinMain` işlevi. Bir framework uygulamasında ancak, yazma `WinMain`. Sınıf kitaplığı tarafından sağlanan ve uygulama açıldığında çağrılır. `WinMain`Pencere sınıflarını kaydetme gibi standart hizmetler gerçekleştirir. Ardından üye işlevlerini başlatın ve uygulamayı çalıştırmak için uygulama nesnesinin çağırır. (Özelleştirebileceğiniz `WinMain` kılarak `CWinApp` üye işlevlerini `WinMain` çağrıları.)  
  
 Uygulamayı başlatmak için `WinMain` , uygulama nesnesinin çağırır `InitApplication` ve `InitInstance` üye işlevleri. Uygulamanın ileti döngüsü çalıştırmak için `WinMain` çağrıları **çalıştırmak** üye işlevi. Sonlandırma üzerinde `WinMain` uygulama çağıran `ExitInstance` üye işlevi.  
  
> [!NOTE]
>  Gösterilen adları **kalın** bu belgede Microsoft Foundation Class Kitaplığı ve Visual C++ tarafından sağlanan öğe gösterir. Gösterilen adları `monospaced` oluşturamaz veya geçersiz kılamazsınız öğelerin türünü belirtir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Genel MFC konuları](../mfc/general-mfc-topics.md)   
 [CWinApp ve MFC Uygulama Sihirbazı](../mfc/cwinapp-and-the-mfc-application-wizard.md)   
 [Geçersiz kılınabilir CWinApp üye işlevleri](../mfc/overridable-cwinapp-member-functions.md)   
 [Özel CWinApp Hizmetleri](../mfc/special-cwinapp-services.md)

