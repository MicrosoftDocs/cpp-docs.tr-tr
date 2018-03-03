---
title: "--Oluşturucular yorum | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- constructors comment
- declarations, constructors
- MFC source files, Constructors comment
- declaring constructors, code comments
- comments, MFC
- comments, constructors comment
- constructors [MFC], declaring
- instance constructors, code comments
ms.assetid: f400774e-ba85-49ed-85b7-70ef2f7dcb2b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1f6425252df34936d4ba3c9013664205b0038d82
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="-constructors-comment"></a>// Oluşturucu Açıklaması
`// Constructors` Bölümü bir MFC sınıf bildiriminin bildirir gerçekten nesne kullanmak için gereken tüm başlatma işlevler yanı sıra kurucularda (C++ algılama). Örneğin, `CWnd::Create` önce kullandığınız oluşturucular bölümünde çünkü `CWnd` nesnesi, onu gerekir "tam olarak oluşturulmasını" C++ Oluşturucusu çağrılmadan ve ardından çağırma **oluşturma** işlevi. Genellikle, bu ortak üyeleridir.  
  
 Örneğin, sınıf `CStdioFile` biri altında listesinde gösterildiğini üç Oluşturucusu vardır [açıklamalara bir örnek](../mfc/an-example-of-the-comments.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC kaynak dosyalarını kullanma](../mfc/using-the-mfc-source-files.md)   
 [Uygulama açıklaması](../mfc/decrement-implementation-comment.md)   
 [Özniteliklerle ilgili açıklama](../mfc/decrement-attributes-comment.md)   
 [/ / İşlem açıklaması](../mfc/decrement-operations-comment.md)   
 [Geçersiz kılınabilir açıklama](../mfc/decrement-overridables-comment.md)

