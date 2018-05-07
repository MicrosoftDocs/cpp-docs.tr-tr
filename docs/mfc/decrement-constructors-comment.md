---
title: --Oluşturucular yorum | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 71b78e74b4b8d974fceaf5f854c9890cd7cdd1a1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
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

