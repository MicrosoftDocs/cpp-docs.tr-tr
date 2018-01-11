---
title: MAPI | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- messaging [MFC], client applications
- enabling applications for MAPI [MFC]
- MAPI support in MFC
- e-mail [MFC], enabling
- mail [MFC], enabling your application
- MAPI, MFC
- enabling applications for mail [MFC]
ms.assetid: 193449f7-b131-4ab0-9301-8d4f6cd1e7c4
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: de955ecc25137f5305806ca5ba03ed15930574dd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="mapi"></a>MAPI
Bu makalede, istemci ileti uygulama geliştiricileri için Microsoft ileti uygulama programlama arabirimi (MAPI) açıklanmaktadır. MFC sağlayan bir MAPI alt sınıfında desteği **CDocument** tüm API'larını değil ancak. Daha fazla bilgi için bkz: [MFC içinde MAPI desteği](../mfc/mapi-support-in-mfc.md).  
  
 MAPI, posta etkinleştirilmiş ve posta algılayan uygulamaları oluşturmak, yönetmek, aktarım ve posta iletileri depolamak için kullandığınız işlevleri kümesidir. Uygulama geliştiricilerinin amacı ve posta iletileri içeriğini tanımlamak için Araçlar verir ve bunları kendi saklı posta iletileri Yönetimi'nde esnekliği sağlar. MAPI uygulama geliştiricileri, posta etkinleştirilmiş oluşturmak için kullanabileceğiniz ortak bir arabirim ve posta kullanan uygulamalar temel alınan ileti sistemi bağımsız de sağlar.  
  
 İleti sistemi istemcileri ile Microsoft Windows ileti sistemi (WMS) etkileşim için İnsan bir arabirim sağlar. Bu etkileşimi genellikle ileti depolar ve adres defterleri gibi MAPI uyumlu sağlayıcılardan Hizmetleri isteyen içerir.  
  
 MAPI hakkında daha fazla bilgi için Windows SDK'ın altında Kılavuzu Win32 ileti (MAPI) içinde makalelerine bakın.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [MFC’de MAPI Desteği](../mfc/mapi-support-in-mfc.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CDocument::OnFileSendMail](../mfc/reference/cdocument-class.md#onfilesendmail)   
 [CDocument::OnUpdateFileSendMail](../mfc/reference/cdocument-class.md#onupdatefilesendmail)   
 [COleDocument::OnFileSendMail](../mfc/reference/coledocument-class.md#onfilesendmail)

