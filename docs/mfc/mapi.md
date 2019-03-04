---
title: MAPI
ms.date: 11/04/2016
helpviewer_keywords:
- messaging [MFC], client applications
- enabling applications for MAPI [MFC]
- MAPI support in MFC
- e-mail [MFC], enabling
- mail [MFC], enabling your application
- MAPI, MFC
- enabling applications for mail [MFC]
ms.assetid: 193449f7-b131-4ab0-9301-8d4f6cd1e7c4
ms.openlocfilehash: a5f60e1ba8c2b68ddca312859694f532e38da965
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57279113"
---
# <a name="mapi"></a>MAPI

Bu makalede, istemci ileti uygulaması geliştiricileri için Microsoft ileti uygulama programlama arabirimi (MAPI) açıklanmaktadır. MFC MAPI sınıfındaki bir alt kümesi için destek sağlayan `CDocument` tüm API'larını değil ancak. Daha fazla bilgi için [MFC'de MAPI desteği](../mfc/mapi-support-in-mfc.md).

MAPI, posta etkinleştirilmiş ve posta kullanan uygulamalar oluşturma, düzenleme, aktarımı ve e-posta iletilerini kullanan işlevler kümesidir. Uygulama geliştiricileri amacı ve posta mesajlarının içeriğini tanımlamak için gereken araçları sağlar ve bunları kendi saklı posta iletilerini Yönetimi'nde esnekliği sağlar. MAPI Ayrıca uygulama geliştiricilerin, posta özellikli oluşturmak için kullanabileceğiniz ortak bir arabirim ve temel alınan bir Mesajlaşma sistemi bağımsız posta kullanan uygulamalar sağlar.

İleti sistemi istemcileri ile Microsoft Windows ileti sistemi (WMS) etkileşim için bir insan arabirimi sağlar. Bu etkileşimi genellikle MAPI uyumlu sağlayıcılarından adres defterlerini ve ileti depoları gibi hizmetleri isteyen içerir.

Windows SDK'sı Kılavuzu Win32 Mesajlaşma (MAPI) içinde altında makalelerinin MAPI hakkında daha fazla bilgi için bkz.

## <a name="in-this-section"></a>Bu Bölümde

[MFC’de MAPI Desteği](../mfc/mapi-support-in-mfc.md)

## <a name="see-also"></a>Ayrıca bkz.

[CDocument::OnFileSendMail](../mfc/reference/cdocument-class.md#onfilesendmail)<br/>
[CDocument::OnUpdateFileSendMail](../mfc/reference/cdocument-class.md#onupdatefilesendmail)<br/>
[COleDocument::OnFileSendMail](../mfc/reference/coledocument-class.md#onfilesendmail)
