---
title: "ATL ve MFC arasında seçim önerileri | Microsoft Docs"
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
- MFC, ATL support
- ATL, vs. MFC
ms.assetid: 269325bb-11a8-4330-ad2b-a14a2458679e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 079784f1fed84ae073767a4a0b622d3fdbf7384b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="recommendations-for-choosing-between-atl-and-mfc"></a>ATL ve MFC arasında seçim önerileri
Bileşenleri ve uygulamaları geliştirirken arasında iki yaklaşım seçebilirsiniz — ATL ve MFC (Microsoft Foundation Class Kitaplığı).  
  
## <a name="using-atl"></a>ATL kullanarak  
 ATL hem C++'da bir COM bileşeni oluşturma ve küçük bir yer korumak için hızlı ve kolay bir yoludur. ATL tüm MFC otomatik olarak sağlar yerleşik işlevselliği gerekmiyorsa, bir denetim oluşturmak için kullanın.  
  
## <a name="using-mfc"></a>MFC kullanma  
 MFC tam uygulamaları, ActiveX denetimlerini ve etkin belgeler oluşturmanıza olanak sağlar. MFC ile bir denetim zaten oluşturduysanız, geliştirme MFC'de devam etmek istiyor. Yeni bir denetim oluştururken, tüm MFC'nin yerleşik işlevselliğini gerekmiyorsa ATL kullanmayı düşünün.  
  
## <a name="using-atl-in-an-mfc-project"></a>MFC projesinde ATL kullanma  
 Bir sihirbaz çalıştırarak var olan bir MFC projesinde ATL kullanma desteği ekleyebilirsiniz. Ayrıntılar için bkz [MFC projenize ATL desteği ekleme](../mfc/reference/adding-atl-support-to-your-mfc-project.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ATL’ye Giriş](../atl/introduction-to-atl.md)

