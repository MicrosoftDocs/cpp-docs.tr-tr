---
title: --Geçersiz kılınabilir yorum | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Overridables comment in MFC source files
- MFC source files, Overridables comment
- overriding, Overridables comment in MFC source files
- comments, MFC
ms.assetid: 8968dea5-0d94-451f-bcb2-991580e65ba2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1b71d61175e5446ac33dd0ff6a011d06f601b5a1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33345394"
---
# <a name="-overridables-comment"></a>// Geçersiz Kılınabilen Öğelerle İlgili Açıklama
`// Overridables` Bir MFC sınıf bildirimi bölümü temel sınıf davranışını değiştirmek gerektiğinde, türetilen bir sınıfta geçersiz kılabilirsiniz sanal işlevler içerir. Kesinlikle gerekli olmasa da bunlar genellikle "ile", başlangıç olarak adlandırılır. Burada işlevleri geçersiz kılınması, genellikle uygulamak veya "geri çağırma" veya "bağlayın." çeşit sağlamak için tasarlanmıştır Genellikle, bu üyeler korunur.  
  
 MFC'de kendisi, saf sanal işlevler her zaman bu bölümde yerleştirilir. Saf sanal işlevi c++ formun biridir:  
  
 `virtual void OnDraw( ) = 0;`  
  
 Sınıfından listeleme örnekteki `CStdioFile`, [açıklamalara bir örnek](../mfc/an-example-of-the-comments.md), liste geçersiz kılınabilir bölüm içerir. Sınıf **CDocument**, diğer yandan, yaklaşık olarak 10 geçersiz kılınabilir üye işlevleri listeler.  
  
 Bazı sınıflarda açıklama da görebilirsiniz `// Advanced Overridables`. Yalnızca gelişmiş işlevler bunlar programcıları geçersiz kılmak denemesi. Büyük olasılıkla asla kılınacağını gerekecektir.  
  
> [!NOTE]
>  Bu makalede açıklanan kuralları aynı zamanda da genel olarak, otomasyon (önceki adıyla OLE Otomasyon bilinir) yöntemleri ve özellikleri için çalışır. Otomasyon yöntemleri MFC işlemleri benzerdir. Otomasyon özellikleri, MFC öznitelikleri benzerdir. MFC geçersiz kılınabilir üye işlevleri (eski adıyla OLE denetimleri ActiveX denetimleri için desteklenir) Otomasyon olayları benzerdir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC kaynak dosyalarını kullanma](../mfc/using-the-mfc-source-files.md)   
 [Açıklamalara bir örnek](../mfc/an-example-of-the-comments.md)   
 [Uygulama açıklaması](../mfc/decrement-implementation-comment.md)   
 [/ / Oluşturucu açıklaması](../mfc/decrement-constructors-comment.md)   
 [Özniteliklerle ilgili açıklama](../mfc/decrement-attributes-comment.md)   
 [/ / İşlem açıklaması](../mfc/decrement-operations-comment.md)

