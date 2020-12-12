---
description: 'Daha fazla bilgi edinin: özelleştirmenin güvenlik etkileri'
title: Özelleştirmenin Güvenlikle İlgili Etkileri
ms.date: 11/04/2016
helpviewer_keywords:
- security, MFC Feature Pack
- MFC Feature Pack, security
ms.assetid: 9be96b12-be38-43bd-a133-5d671265f7a1
ms.openlocfilehash: 64a1029dd3486e3cd653f5e692aa1a14ba6f82b5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97217763"
---
# <a name="security-implications-of-customization"></a>Özelleştirmenin Güvenlikle İlgili Etkileri

Bu konu, MFC 'de olası bir güvenlik zayıflığından bahseder.

## <a name="potential-security-weakness"></a>Olası güvenlik zayıflıkları

MFC, kullanıcının bir uygulama kullanıcı arabiriminin görünüşünü (örneğin, düğmelerin ve simgelerin görünümü) özelleştirmesini sağlar. MFC Ayrıca Kullanıcı tanımlı araçları destekler, bu da kullanıcının kabuk komutlarını yürütmesine izin verir. Uygulamanın özelleştirilmiş ayarları kayıt defterindeki Kullanıcı profiline kaydedildiğinden, bir güvenlik açığı ortaya çıkar. Kayıt defterine erişebilen herkes bu ayarları düzenleyebilir ve uygulama görünümünü veya davranışını değiştirebilir. Örneğin, bilgisayardaki bir yönetici, kullanıcının uygulamasına rastgele programlar (bir ağ paylaşımından bile) yürütmesine neden olarak bir kullanıcının kimliğine bürünebilir.

## <a name="workarounds"></a>Geçici Çözümler

Kayıt defterindeki güvenlik açıklarını kapatmak için bu üç yolu öneririz:

- Orada depolanan verileri şifreleyin

- Verileri kayıt defteri yerine güvenli bir dosyada depolayın.

   Bu ilk iki yöntemden birini gerçekleştirmek için [Csettingsstorage sınıfından](../mfc/reference/csettingsstore-class.md) bir sınıf türetirsiniz ve kayıt defteri dışında şifreleme veya depolama uygulamak için yöntemlerini geçersiz kılın.

- Ayrıca, uygulamanızdaki özelleştirmeleri devre dışı bırakabilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[MFC için Özelleştirme](../mfc/customization-for-mfc.md)
