---
title: Internet Güvenliği (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- code signing [MFC], Internet security
- sandboxing [MFC]
- digital signatures [MFC], Internet security
- code signing [MFC]
- Web application security [MFC]
- code access security [MFC], Internet security considerations
- security [MFC]
- security [MFC], Internet
- Internet applications [MFC], security
- Web application security [MFC], Internet security approaches
ms.assetid: bf0da697-81bc-41f0-83fa-d7f82ed83df8
ms.openlocfilehash: 184c8edf3e4a81be1f8b2a282a0db9758a75253f
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57259535"
---
# <a name="internet-security-c"></a>Internet Güvenliği (C++)

Kod güvenliği geliştiriciler ve kullanıcılar Internet uygulamaları için önemli bir sorun var. Riskleri vardır: kötü amaçlı kod, üzerinde oynanmış kod ve bilinmeyen siteleri veya yazarlar koddan.

İnternet'e geliştirirken güvenlik için iki temel yaklaşım vardır. İlk "korumalı alana alma." olarak adlandırılır Bu yaklaşımda, bir uygulama belirli bir API kümesi için kısıtlı ve potansiyel olarak tehlikeli olabilecek olanlar gibi bir program, verileri bir kullanıcının bilgisayarında nereye yok edebilir ve dosya g/ç dışında tutulması. İkincisi, dijital imzalar kullanılarak uygulanır. Bu yaklaşım için "shrinkwrap" İnternet'e adlandırılır. Kod doğrulanır ve özel anahtarı/genel anahtar teknolojisi kullanılarak imzalanmış. Kod çalıştırmadan önce kodu bilinen bir kimliği doğrulanmış kaynaktan olduğunu ve imzalanmış olduğundan'ın kodunu değiştirilmediğinden emin olmak için dijital imzasını doğrulandı.

Bu durumda, uygulamanın herhangi bir zarar yapmaz ve uygulama kaynağı güven güven. İkinci, dijital imzalar, orjinalliği doğrulamak için kullanılır. Dijital imza tanımlamak ve kod yayımcısı ayrıntılarını sağlamak için kullanılan bir endüstri standardıdır. Bu teknoloji, RSA ve X.509 dahil olmak üzere standartlarını temel alır. Tarayıcılar, genellikle bunlar indirip bilinmeyen kaynaklardan gelen kodu çalıştırmak isteyip istemediklerini açmasına imkan tanıyın.

## <a name="see-also"></a>Ayrıca bkz.

[MFC Internet Programlama Görevleri](../mfc/mfc-internet-programming-tasks.md)<br/>
[MFC Internet Programlama Temelleri](../mfc/mfc-internet-programming-basics.md)
