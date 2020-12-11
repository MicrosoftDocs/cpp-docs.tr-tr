---
description: 'Daha fazla bilgi edinin: ATL ve MFC arasında seçim yapma önerileri'
title: ATL ve MFC arasında seçim önerileri
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, ATL support
- ATL, vs. MFC
ms.assetid: 269325bb-11a8-4330-ad2b-a14a2458679e
ms.openlocfilehash: 506df04ebbd3bc9079e1d40cf14773d9d9a6bd1a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97159160"
---
# <a name="recommendations-for-choosing-between-atl-and-mfc"></a>ATL ve MFC arasında seçim önerileri

Bileşenler ve uygulamalar geliştirirken, iki yaklaşım arasından (ATL ve MFC) (Microsoft Foundation Class Kitaplığı) seçim yapabilirsiniz.

## <a name="using-atl"></a>ATL kullanma

ATL, C++ ' da bir COM bileşeni oluşturmak ve küçük bir ayak izi sürdürmek için hızlı ve kolay bir yoldur. MFC 'nin otomatik olarak sağladığı yerleşik işlevselliğe gerek yoksa bir denetim oluşturmak için ATL kullanın.

## <a name="using-mfc"></a>MFC kullanma

MFC, tam uygulamalar, ActiveX denetimleri ve etkin belgeler oluşturmanıza olanak sağlar. MFC ile zaten bir denetim oluşturduysanız, MFC 'de geliştirmeye devam etmek isteyebilirsiniz. Yeni bir denetim oluştururken, MFC 'nin yerleşik işlevselliğine ihtiyaç duymuyorsanız ATL kullanmayı düşünün.

## <a name="using-atl-in-an-mfc-project"></a>Bir MFC projesinde ATL kullanma

Bir Sihirbazı çalıştırarak mevcut bir MFC projesinde ATL kullanma desteği ekleyebilirsiniz. Ayrıntılar için bkz. [MFC PROJENIZE atl desteği ekleme](../mfc/reference/adding-atl-support-to-your-mfc-project.md).

## <a name="see-also"></a>Ayrıca bkz.

[ATL'ye Giriş](../atl/introduction-to-atl.md)
