---
title: MAPI | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- messaging [MFC], client applications
- enabling applications for MAPI [MFC]
- MAPI support in MFC
- e-mail [MFC], enabling
- mail [MFC], enabling your application
- MAPI, MFC
- enabling applications for mail [MFC]
ms.assetid: 193449f7-b131-4ab0-9301-8d4f6cd1e7c4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b2ca182da3a0300604415b790c0aba138c8fd7a2
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46439113"
---
# <a name="mapi"></a>MAPI

Bu makalede, istemci ileti uygulaması geliştiricileri için Microsoft ileti uygulama programlama arabirimi (MAPI) açıklanmaktadır. MFC MAPI sınıfındaki bir alt kümesi için destek sağlayan `CDocument` tüm API'larını değil ancak. Daha fazla bilgi için [MFC'de MAPI desteği](../mfc/mapi-support-in-mfc.md).

MAPI, posta etkinleştirilmiş ve posta kullanan uygulamalar oluşturma, düzenleme, aktarımı ve e-posta iletilerini kullanan işlevler kümesidir. Uygulama geliştiricileri amacı ve posta mesajlarının içeriğini tanımlamak için gereken araçları sağlar ve bunları kendi saklı posta iletilerini Yönetimi'nde esnekliği sağlar. MAPI Ayrıca uygulama geliştiricilerin, posta özellikli oluşturmak için kullanabileceğiniz ortak bir arabirim ve temel alınan bir Mesajlaşma sistemi bağımsız posta kullanan uygulamalar sağlar.

İleti sistemi istemcileri ile Microsoft Windows ileti sistemi (WMS) etkileşim için bir insan arabirimi sağlar. Bu etkileşimi genellikle MAPI uyumlu sağlayıcılarından adres defterlerini ve ileti depoları gibi hizmetleri isteyen içerir.

Windows SDK'sı Kılavuzu Win32 Mesajlaşma (MAPI) içinde altında makalelerinin MAPI hakkında daha fazla bilgi için bkz.

## <a name="in-this-section"></a>Bu Bölümde

[MFC’de MAPI Desteği](../mfc/mapi-support-in-mfc.md)

## <a name="see-also"></a>Ayrıca Bkz.

[CDocument::OnFileSendMail](../mfc/reference/cdocument-class.md#onfilesendmail)<br/>
[CDocument::OnUpdateFileSendMail](../mfc/reference/cdocument-class.md#onupdatefilesendmail)<br/>
[COleDocument::OnFileSendMail](../mfc/reference/coledocument-class.md#onfilesendmail)

