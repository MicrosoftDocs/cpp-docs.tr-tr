---
title: Önemli hata C1128
ms.date: 11/04/2016
f1_keywords:
- C1128
helpviewer_keywords:
- C1128
ms.assetid: 6f9580fd-ecef-48be-9780-dcf666704279
ms.openlocfilehash: 64671c9abe8ed1375df1e91ca7509e6a597366ee
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80203663"
---
# <a name="fatal-error-c1128"></a>Önemli hata C1128

Bölüm sayısı nesne dosyası biçimi sınırını aştı:/bigobj ile derle

Bir. obj dosyası, bir COFF nesne dosya biçimi sınırlaması olan, izin verilen bölüm sayısını aştı.

Bu bölüm sınırlamasından ulaşmak, [/GY](../../build/reference/gy-enable-function-level-linking.md) ve bir hata ayıklama derlemesi kullanmanın sonucu olabilir; **/GY** işlevlerin kendi COMDAT bölümlerine gitmesini sağlar. Bir hata ayıklama derlemesinde, her COMDAT işlevi için bir hata ayıklama bilgileri bölümü vardır.

C1128, çok fazla satır içi işlev olduğunda da oluşabilir.

Bu hatayı düzeltmek için, kaynak dosyanızı birden çok kaynak kodu dosyasına bölün, **/GY**olmadan derleyin veya [/bigobj ile derleyin (Içindeki bölüm sayısını artırın. Obj dosyası)](../../build/reference/bigobj-increase-number-of-sections-in-dot-obj-file.md).  **/GY**ile derleme yapmazsanız, **/O2** ve **/O1** her ikisi de **/GY**olduğundan iyileştirmeleri tek tek belirtmeniz gerekecektir.

Mümkünse, hata ayıklama bilgisi olmadan derleyin.

Ayrıca, derleyicinin bunları yaymasına izin vermek yerine ayrı kaynak kodu dosyalarında şablonların belirli örneklemelerinden de sahip olmanız gerekebilir.

Kod taşıma sırasında, C1128 büyük olasılıkla x64 derleyicisini kullanırken ve daha sonra x86 derleyicisi ile görünür. x64, her bir işlevle derlenen **/GY** veya şablon ya da sınıf satır içi: kod, pveri ve hata ayıklama bilgileri ve muhtemelen XData 'dan satır içine alınmış olan en az 4 bölümden oluşur.  X86, PDATA olmayacak.
