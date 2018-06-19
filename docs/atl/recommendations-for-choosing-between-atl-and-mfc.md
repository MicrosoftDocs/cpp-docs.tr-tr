---
title: ATL ve MFC arasında seçim önerileri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC, ATL support
- ATL, vs. MFC
ms.assetid: 269325bb-11a8-4330-ad2b-a14a2458679e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 116f2066b98951aa2a470021f5527542ac8cbe46
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32357329"
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

