---
description: 'Daha fazla bilgi edinin: Uluslararası etkinleştirme'
title: Uluslararası Etkinleştirme
ms.date: 11/04/2016
helpviewer_keywords:
- globalization [C++], character sets
- strings [C++], international enabling
- localization [C++], character sets
- MBCS [C++], enabling
- Unicode [C++], enabling
ms.assetid: b077f4ca-5865-40ef-a46e-d9e4d686ef21
ms.openlocfilehash: 15db7e27b65f4225917945820c936e572fc5da94
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97207273"
---
# <a name="international-enabling"></a>Uluslararası Etkinleştirme

En geleneksel C ve C++ kodu, uluslararası uygulamalar için iyi çalışmayan karakter ve dize düzenlemesi hakkında varsayımlar yapar. Hem MFC hem de çalışma zamanı kitaplığı Unicode veya MBCS 'yi destekleirken, sizin için hala iş yapmanız gerekir. Size kılavuzluk etmek için, bu bölümde Visual C++ "Uluslararası etkinleştirme" öğesinin anlamı açıklanmaktadır:

- Hem Unicode hem de MBCS MFC işlev parametresi listelerinde ve dönüş türlerinde taşınabilir veri türleri aracılığıyla etkinleştirilir. Bu türler, yapılarınızın simgeyi `_UNICODE` veya sembolünü `_MBCS` (DBCS anlamına gelir) tanımlayıp tanımlamadığına bağlı olarak, uygun yollarla koşullu olarak tanımlanır. Farklı MFC kitaplıklarının çeşitleri, derlemenize ait bu iki sembolden hangisinin tanımladığına bağlı olarak uygulamanızla otomatik olarak bağlanır.

- Sınıf kitaplığı kodu, doğru Unicode veya MBCS davranışını sağlamak için taşınabilir çalışma zamanı işlevlerini ve diğer yolları kullanır.

- Kodunuzda bazı uluslararası duruma getirme görevlerini yine de işlemeniz gerekir:

  - MFC 'yi her iki ortamda da taşınabilir hale getirmek için aynı taşınabilir çalışma zamanı işlevlerini kullanın.

  - Makroyu kullanarak her iki ortamda da sabit dizeler ve karakterler taşınabilir yapın `_T` . Daha fazla bilgi için, bkz. [Tchar. h 'de Genel metin eşlemeleri](../text/generic-text-mappings-in-tchar-h.md).

  - MBCS altındaki dizeleri ayrıştırırken önlem alın. Bu önlemler Unicode altında gerekli değildir. Daha fazla bilgi için bkz. [MBCS programlama ipuçları](../text/mbcs-programming-tips.md).

  - Uygulamanızda ANSI (8 bit) ve Unicode (16 bit) karakterlerini karıştırırsanız dikkatli olabilirsiniz. Programınızın bazı bölümlerinde, diğer bir deyişle, diğer bir deyişle, diğer bir deyişle bunları aynı dizede karıştırabilmeniz mümkündür.

  - Uygulamanızda sabit kod dizeleri vermeyin. Bunun yerine, bunları uygulamanın. rc dosyasına ekleyerek STRINGTABLE kaynakları yapın. Uygulamanız daha sonra kaynak kodu değişiklikleri veya yeniden derleme gerekmeden yerelleştirilebilecek. STRINGTABLE kaynakları hakkında daha fazla bilgi için bkz. [dize düzenleyici](../windows/string-editor.md).

> [!NOTE]
> Avrupa ve MBCS karakter kümelerinin aksanlı harfler gibi bazı karakterleri (örneğin, 0x80 ' dan büyük karakter kodları) vardır. Çoğu kod imzalı karakterler kullandığından, 0x80 ' dan büyük olan bu karakterler öğesine dönüştürüldüğünde işaret genişletilir **`int`** . Bu dizi dizin oluşturma için bir sorun olduğundan, işaret genişletilmiş karakterler, negatif, dizi dışında dizinler. Japonca gibi MBCS kullanan diller de benzersizdir. Bir karakter 1 veya 2 bayttan oluşabileceğinden, her iki baytı de aynı anda tek yapmanız gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[Unicode ve MBCS](../text/unicode-and-mbcs.md)<br/>
[Uluslararası duruma getirme stratejileri](../text/internationalization-strategies.md)
