---
title: ATL ile MFC arasında seçim önerileri
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, ATL support
- ATL, vs. MFC
ms.assetid: 269325bb-11a8-4330-ad2b-a14a2458679e
ms.openlocfilehash: e4e51f81bbdc54ff09980acfba22037df77abac9
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57259782"
---
# <a name="recommendations-for-choosing-between-atl-and-mfc"></a>ATL ile MFC arasında seçim önerileri

Bileşenler ve uygulamalar geliştirirken, iki yaklaşım arasında seçim yapabilirsiniz; ATL ve MFC (Microsoft Foundation Class Library).

## <a name="using-atl"></a>ATL kullanarak

ATL, hem c++'ta bir COM bileşeni oluşturma ve küçük ayak izine korumak için hızlı ve kolay bir yoludur. ATL, MFC otomatik olarak sağlayan yerleşik işlevlerin ihtiyacınız yoksa, bir denetim oluşturmak için kullanın.

## <a name="using-mfc"></a>MFC kullanma

MFC tüm uygulamalara, ActiveX denetimleri ve etkin belgeler oluşturmanıza olanak sağlar. MFC ile bir denetimi zaten oluşturduysanız, MFC'de geliştirmeye devam etmek isteyebilirsiniz. Yeni bir denetim oluştururken, tüm MFC'nin yerleşik işlevler gerekmiyorsa, ATL kullanarak göz önünde bulundurun.

## <a name="using-atl-in-an-mfc-project"></a>Bir MFC projesinde ATL Kullanımı

Bir sihirbaz çalıştırarak var olan bir MFC projesinde ATL kullanma desteği ekleyebilirsiniz. Ayrıntılar için bkz [MFC projenize ATL desteği ekleme](../mfc/reference/adding-atl-support-to-your-mfc-project.md).

## <a name="see-also"></a>Ayrıca bkz.

[ATL’ye Giriş](../atl/introduction-to-atl.md)
