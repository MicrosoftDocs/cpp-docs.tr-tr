---
title: Genel dil değişiklikleri (C + +/ CLI) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 79a70768-225c-4ae2-84d1-178b20a9b042
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 9b48ebdf0bf25399b08f8a1cb1240a857cfad352
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46418469"
---
# <a name="general-language-changes-ccli"></a>Genel Dil Değişiklikleri (C++/CLI)

Yönetilen Uzantılar'dan C++ için Visual C++ için değiştirildi. CLR dil özellikleri sayısı.

Bu bölümde açıklanan bir tür dil derlemesidir değişikliklerdir. Dize değişmez değerleri, üç nokta arasında aşırı yükleme çözünürlüğü içinde bir değişiklik işleme bir değişiklik içerir ve `Param` özniteliği, değişikliği `typeof` için `typeid`, arama oluşturucu başlatıcı listelerinin bir değişikliği ve Yeni bir atama gösterimi sunulmasıyla, `safe_cast`.

[Değişmez Dize Değeri](../dotnet/string-literal.md)<br/>
Dize değişmez değerleri işlenmesini nasıl değiştiğini açıklanır.

[Param Dizisi ve Üç Nokta](../dotnet/param-array-and-ellipsis.md)<br/>
Açıklar nasıl `ParamArray` artık, üç nokta üzerinde öncelik verilir (`...`) değişen sayıda bağımsız değişkenler kullanarak işlev çağrılarını çözümlemek için.

[typeof T::typeid'e gider](../dotnet/typeof-goes-to-t-typeid.md)<br/>
Açıklar nasıl `typeof` işleci supplanted tarafından `typeid`.

[Başlatıcı Listeleri](../dotnet/initializer-lists.md)<br/>
Başlatıcı Listeleri arama sırası değişiklikleri anlatır.

[Dönüştürme Gösterimi ve safe_cast<> Konusuna Giriş](../dotnet/cast-notation-and-introduction-of-safe-cast-angles.md)<br/>
Değişiklikler atama gösterimi ve belirli sunulmasıyla tartışılır `safe_cast`.

## <a name="see-also"></a>Ayrıca Bkz.

[C++/CLI Geçiş Öncüsü](../dotnet/cpp-cli-migration-primer.md)