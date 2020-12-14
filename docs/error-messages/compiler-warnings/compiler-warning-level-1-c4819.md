---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4819'
title: Derleyici Uyarısı (düzey 1) C4819
ms.date: 04/08/2019
f1_keywords:
- C4819
helpviewer_keywords:
- C4819
ms.assetid: c0316e85-249c-414d-9df0-622d077c6bc2
ms.openlocfilehash: 871a861f7860f8561fb830cc6a19980af7726174
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97198225"
---
# <a name="compiler-warning-level-1-c4819"></a>Derleyici Uyarısı (düzey 1) C4819

> Dosya geçerli kod sayfasında (*sayı*) gösterilemeyen bir karakter içeriyor. Veri kaybını engellemek için dosyayı Unicode biçiminde kaydedin.

C4819, dosyadaki tüm karakterleri temsil eden bir kod sayfası kullanarak sistemde bir ANSI Kaynak dosyası derlerken oluşur.

C4819 çözümlemek için birkaç yol vardır. Tek bir basit yol, izin verilmeyen karakteri (örneğin, bir açıklamada varsa) kaldırmak olur. Denetim Masası 'ndaki sistem kod sayfasını, kaynak kodunuz tarafından kullanılan karakter kümesini destekleyen bir olacak şekilde ayarlayabilirsiniz. Kaynak kodunuzda yalnızca temel ANSI karakter kümesini kullanan karakterler veya dizeler oluşturmak için Unicode [kaçış dizilerini](../../c-language/escape-sequences.md) kullanabilirsiniz. Son olarak, dosyayı bir Unicode biçiminde, bir imza ile, bayt sırası işareti (BOM) olarak da bilinen bir imzayla kaydedebilirsiniz.

Unicode biçiminde bir dosyayı kaydetmek için, Visual Studio 'da **Dosya**  >  **farklı kaydet**' i seçin. **Dosyayı farklı kaydet** Iletişim kutusunda **Kaydet** düğmesini seçin ve **kodlamayla kaydet**' i seçin. Aynı dosya adına kaydederseniz, dosyayı değiştirmek istediğinizi onaylamanız gerekebilir. **Gelişmiş kaydetme seçenekleri** iletişim kutusunda dosyadaki tüm karakterleri temsil eden bir kodlama seçin — örneğin, **UNICODE (imzayla UTF-8)-CodePage 65001**— ve ardından **Tamam**' ı seçin.
