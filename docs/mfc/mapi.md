---
description: 'Daha fazla bilgi edinin: MAPI'
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
ms.openlocfilehash: 634d5d0b2dbbc8a262f624be2b7e294ef6069b96
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97280813"
---
# <a name="mapi"></a>MAPI

Bu makalede, istemci ileti uygulaması geliştiricileri için Microsoft mesajlaşma uygulaması programlama arabirimi (MAPI) açıklanmaktadır. MFC, sınıftaki bir MAPI alt kümesi için destek sağlar `CDocument` , ancak tüm API 'yi kapsüllemez. Daha fazla bilgi için bkz. [MFC 'de MAPI desteği](mapi-support-in-mfc.md).

MAPI posta kullanan ve posta kullanan uygulamaların posta iletilerini oluşturmak, işlemek, aktarmak ve depolamak için kullandığı bir işlevler kümesidir. Uygulama geliştiricilere, e-posta iletilerinin amacını ve içeriğini tanımlama ve bunları depolanan posta iletilerinin yönetiminde esneklik sağlayan araçlar sunar. Ayrıca, uygulama geliştiricilerinin, arka plandaki mesajlaşma sisteminden bağımsız olarak posta özellikli ve posta duyarlı uygulamalar oluşturmak için kullanabileceği ortak bir arabirim de sağlar.

Mesajlaşma istemcileri, Microsoft Windows mesajlaşma sistemi (WMS) ile etkileşim için bir insan arabirimi sağlar. Bu etkileşim genellikle ileti depoları ve adres defterleri gibi MAPI ile uyumlu sağlayıcılardan hizmet istemeyi içerir.

MAPI hakkında daha fazla bilgi için Windows SDK Win32 mesajlaşma (MAPI) başlığı altında yer alarak bulunan makalelere bakın.

## <a name="in-this-section"></a>Bu Bölümde

[MFC 'de MAPI desteği](mapi-support-in-mfc.md)

## <a name="see-also"></a>Ayrıca bkz.

[CDocument:: OnFileSendMail](reference/cdocument-class.md#onfilesendmail)<br/>
[CDocument:: OnUpdateFileSendMail](reference/cdocument-class.md#onupdatefilesendmail)<br/>
[Cotadocument:: OnFileSendMail](reference/coledocument-class.md#onfilesendmail)
