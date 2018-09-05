---
title: ATL ile MFC arasında seçim önerileri | Microsoft Docs
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
ms.openlocfilehash: 0a9bbf30c728b6562da0c56c25b177697f0882a5
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43762131"
---
# <a name="recommendations-for-choosing-between-atl-and-mfc"></a>ATL ile MFC arasında seçim önerileri

Bileşenler ve uygulamalar geliştirirken, iki yaklaşım arasında seçim yapabilirsiniz; ATL ve MFC (Microsoft Foundation Class Library).

## <a name="using-atl"></a>ATL kullanarak

ATL, hem c++'ta bir COM bileşeni oluşturma ve küçük ayak izine korumak için hızlı ve kolay bir yoludur. ATL, MFC otomatik olarak sağlayan yerleşik işlevlerin ihtiyacınız yoksa, bir denetim oluşturmak için kullanın.

## <a name="using-mfc"></a>MFC kullanma

MFC tüm uygulamalara, ActiveX denetimleri ve etkin belgeler oluşturmanıza olanak sağlar. MFC ile bir denetimi zaten oluşturduysanız, MFC'de geliştirmeye devam etmek isteyebilirsiniz. Yeni bir denetim oluştururken, tüm MFC'nin yerleşik işlevler gerekmiyorsa, ATL kullanarak göz önünde bulundurun.

## <a name="using-atl-in-an-mfc-project"></a>Bir MFC projesinde ATL Kullanımı

Bir sihirbaz çalıştırarak var olan bir MFC projesinde ATL kullanma desteği ekleyebilirsiniz. Ayrıntılar için bkz [MFC projenize ATL desteği ekleme](../mfc/reference/adding-atl-support-to-your-mfc-project.md).

## <a name="see-also"></a>Ayrıca Bkz.

[ATL’ye Giriş](../atl/introduction-to-atl.md)

