---
title: "MFC modül durumunda etkinleştirme bağlamları desteği | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- activation contexts [MFC]
- activation contexts [MFC], MFC support
ms.assetid: 1e49eea9-3620-46dd-bc5f-d664749567c7
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a9a15941848a9e8d5bdf35dfebf273f7684fbb8a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="support-for-activation-contexts-in-the-mfc-module-state"></a>MFC Modül Durumunda Etkinleştirme Bağlamları Desteği
MFC kullanıcı modülü tarafından sağlanan bir bildirim kaynağı kullanarak bir etkinleştirme bağlamı oluşturur. Etkinleştirme bağlamları nasıl oluşturulduğunu daha fazla bilgi için aşağıdaki konulara bakın:  
  
-   [Etkinleştirme bağlamları](http://msdn.microsoft.com/library/aa374153)  
  
-   [Uygulama bildirimleri](http://msdn.microsoft.com/library/aa374191)  
  
-   [Derleme bildirimleri](http://msdn.microsoft.com/library/aa374219)  
  
## <a name="remarks"></a>Açıklamalar  
 Bu Windows SDK konular okunurken MFC Windows SDK etkinleştirme bağlamı API kullanmaz dışında MFC etkinleştirme bağlamı mekanizması Windows SDK etkinleştirme bağlamı benzer unutmayın.  
  
 Etkinleştirme bağlamı MFC uygulamaları, kullanıcı DLL'ler ve MFC uzantı DLL'leri aşağıdaki şekillerde çalışır:  
  
-   MFC uygulamaları kendi bildirim kaynağı için kaynak kimliği 1 kullanın. Bu durumda, MFC kendi etkinleştirme bağlamı oluşturmaz, ancak varsayılan uygulama bağlamını kullanır.  
  
-   MFC kullanıcı DLL'leri kendi bildirim kaynağı için kaynak kimliği 2 kullanın. Burada, aynı kitaplıkları (örneğin, ortak denetimler kitaplığı) farklı sürümlerini farklı kullanıcı DLL'leri kullanabilmeniz için MFC her kullanıcı DLL için bir etkinleştirme bağlamı oluşturur.  
  
-   MFC uzantı DLL'leri kendi barındırma uygulamaları veya kullanıcı DLL'leri etkinleştirme bağlamları kurmak için kullanır.  
  
 Etkinleştirme bağlamı durumu altında açıklanan işlemlerde kullanılarak değiştirilebilir ancak [etkinleştirme bağlamı API kullanarak](http://msdn.microsoft.com/library/aa376620), MFC etkinleştirme bağlamı mekanizmasını kullanarak yararlı olabilir DLL tabanlı eklenti mimarileri geliştirirken olduğu değil kolay (veya mümkün değil) etkinleştirme durumu öncesinde ve sonrasında dış eklentiler için çağrıları tek tek el ile geçiş yapmak için.  
  
 Etkinleştirme bağlamı oluşturulan [Afxwinınit](../mfc/reference/application-information-and-management.md#afxwininit). İçinde yok `AFX_MODULE_STATE` yıkıcı. Etkinleştirme bağlamı tanıtıcısı tutulur `AFX_MODULE_STATE`. (`AFX_MODULE_STATE` açıklanan [AfxGetStaticModuleState](reference/extension-dll-macros.md#afxgetstaticmodulestate).)  
  
 [AFX_MANAGE_STATE](reference/extension-dll-macros.md#afx_manage_state) makrosu etkinleştirir ve etkinleştirme içeriği devre dışı bırakır. `AFX_MANAGE_STATE`statik MFC kitaplıkları, yanı sıra MFC DLL'leri kullanıcı DLL tarafından seçilen uygun etkinleştirme bağlamda yürütmek MFC kodu izin vermek için etkindir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Etkinleştirme bağlamları](http://msdn.microsoft.com/library/aa374153)   
 [Uygulama bildirimleri](http://msdn.microsoft.com/library/aa374191)   
 [Derleme bildirimleri](http://msdn.microsoft.com/library/aa374219)   
 [Afxwinınit](../mfc/reference/application-information-and-management.md#afxwininit)   
 [AfxGetStaticModuleState](reference/extension-dll-macros.md#afxgetstaticmodulestate)   
 [AFX_MANAGE_STATE](reference/extension-dll-macros.md#afx_manage_state)

