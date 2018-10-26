---
title: Özelleştirmenin güvenlikle ilgili etkileri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- security, MFC Feature Pack
- MFC Feature Pack, security
ms.assetid: 9be96b12-be38-43bd-a133-5d671265f7a1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2035e665bd7d8cba502c3516498934f32c2b3dd0
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50080851"
---
# <a name="security-implications-of-customization"></a>Özelleştirmenin Güvenlikle İlgili Etkileri

Bu konu, olası bir güvenlik açığına MFC'de açıklar.

## <a name="potential-security-weakness"></a>Olası güvenlik açıklarına neden olabileceği

MFC sağlayan kullanıcı bir uygulama kullanıcı arabirimi, örneğin, düğmeler ve simgeler görünümünü görünümünü özelleştirebilirsiniz. MFC Kabuk komutları yürütmek kullanıcının olanak sağlayan kullanıcı tanımlı araçlar da destekler. Bir güvenlik açığı özelleştirilmiş uygulamanın kayıt defteri kullanıcı profiline kaydedilir doğurur. Kayıt defteri erişebilen herkesin bu ayarları düzenleyebilir ve uygulama görünümünü veya davranışını değiştirin. Örneğin, bilgisayarda yönetici kullanıcının uygulama rasgele programlar (bile bir ağ paylaşımından) yürütmek neden olarak bir kullanıcının kimliğine bürünme.

## <a name="workarounds"></a>Geçici Çözümler

Kayıt defteri güvenlik açıklarını kapatmak için bu üç yoldan herhangi birini öneririz:

- Burada depolanan verileri şifrele

- Kayıt defteri güvenli dosyasında yerine data Store.

   Bu ilk iki yoldan birini gerçekleştirmek için öğesinden bir sınıf türetin [CSettingsStore sınıfı](../mfc/reference/csettingsstore-class.md) ve şifreleme veya kayıt defteri dışında depolama uygulamak için kendi yöntemleri geçersiz kılın.

- Özelleştirmeleri uygulamanızda da devre dışı bırakabilirsiniz.

## <a name="see-also"></a>Ayrıca Bkz.

[MFC için Özelleştirme](../mfc/customization-for-mfc.md)

