---
title: Birlikte Çalışabilirlik için Başarım Düşünceleri (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- /clr compiler option [C++], interop performance considerations
- platform invoke [C++], interoperability
- interop [C++], performance consideraitons
- mixed assemblies [C++], performance considerations
- interoperability [C++], performance considerations
ms.assetid: bb9a282e-c3f8-40eb-a2fa-45d80d578932
ms.openlocfilehash: c6b4456d9c75061c9a8c93f37f98b58f92adc899
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57741850"
---
# <a name="performance-considerations-for-interop-c"></a>Birlikte Çalışabilirlik için Başarım Düşünceleri (C++)

Bu konu, yönetilen veya yönetilmeyen birlikte çalışma geçişleri çalışma zamanı performansı üzerindeki etkisini azaltmak için yönergeler sağlar.

Visual C++, Visual Basic ve C# (P/Invoke) gibi diğer .NET dilleri olarak birlikte çalışabilirlik mekanizmalarının aynısını destekler, ancak Visual C++ (C++ birlikte çalışması) özgü birlikte çalışabilirlik desteği de sağlar. Performans açısından kritik uygulamalar için birlikte çalışma her tekniğin performans etkilerini anlamak önemlidir.

Kullanılan birlikte çalışabilirlik teknik bağımsız olarak, dönüştürücüler denen özel geçiş dizileri, yönetilmeyen bir işlev veya tersine yönetilen bir işlev çağırır her zaman gereklidir. Bu dönüştürücüleri Visual C++ Derleyici tarafından otomatik olarak eklenir, ancak üst üste, bu geçiş performans açısından pahalı olabileceğini göz önünde tutmak önemlidir.

## <a name="reducing-transitions"></a>Geçişleri azaltma

Birlikte çalışma dönüştürücüleri maliyetini azaltmak veya önlemek için bir yol, yönetilen veya yönetilmeyen geçişleri en aza indirmek ilgili arabirimler yeniden düzenlemektir. Yönetilen veya yönetilmeyen sınırında sık çağrıları katılan onlar sık iletişim kuran arabirimler hedefleyerek önemli ölçüde performans yapılabilir. Sıkı bir döngüde yönetilmeyen bir işlev çağıran bir yönetilen Örneğin, iyi bir aday yeniden düzenleme için işlevidir. Döngü yönetilmeyen tarafa taşınır veya yönetilen bir alternatif, yönetilmeyen çağrı oluşturulur (belki de yönetilen tarafında veri olması ve ardından tümünü tek seferde döngüsünden sonra yönetilmeyen API için hazırlama), geçiş sayısı olabilir oturum azaltıldı ificantly.

## <a name="pinvoke-vs-c-interop"></a>P/Invoke vs. C++ Birlikte Çalışma

.NET Visual Basic ve C# gibi diller için yerel bileşenleriyle birlikte önceden belirlenmiş P/Invoke yöntemdir. P/Invoke .NET Framework tarafından desteklenmediği için Visual C++, de destekler, ancak Visual C++ C++ birlikte çalışması adlandırılan kendi birlikte çalışabilirlik desteği de sağlar. P/Invoke tür kullanımı uyumlu olmadığı için C++ birlikte çalışması P/Invoke tercih edilir. Sonuç olarak, hataları çalışma zamanında öncelikli olarak rapor edilir, ancak C++ birlikte çalışması P/Invoke performans avantajları da vardır.

Her iki tekniği, yönetilen bir işlev yönetilmeyen bir işlev çağırdığında gereken birkaç şey gerektirir:

- İşlev çağırma bağımsız değişkenlerinde CLR'den yerel türler için hazırlanırlar.

- Yönetilmeyen bir dönüştürücü yürütülür.

- Yönetilmeyen işlev (bağımsız değişkenler yerel sürümlerini kullanarak) adı verilir.

- Yönetilen için yönetilmeyen bir dönüştürücü yürütülür.

- Dönüş türü ve "dışarı" veya "içinde out" bağımsız değişkenleri CLR'den CLR türleri için yerel.

Yönetilen veya yönetilmeyen dönüştürücüleri çalışması birlikte çalışması için gerekli olan, ancak söz konusu veri türlerine, işlev imzası ve veriler nasıl kullanılacak gerekli olan veri hazırlama bağlıdır.

C++ birlikte çalışması tarafından gerçekleştirilen veri hazırlama basit olası formu şöyledir: parametreler yalnızca yönetilen ve yönetilmeyen sınır bit düzeyinde bir biçimde; arasında kopyalanır hiçbir dönüştürme hiç gerçekleştirilir. P/Invoke için yalnızca basit, tüm parametrelerin doğru budur blittable türleri. Aksi takdirde, yönetilen her parametreyi uygun yerel bir tür için dönüştürmek için güçlü adımlar P/Invoke gerçekleştirir ve tam tersi bağımsız değişkenler "çıkış" işaretlenmişse veya "içinde out".

Diğer bir deyişle, P/Invoke en güçlü yöntemi kullanan C++ birlikte çalışması veri hazırlama, olası en hızlı yöntemi kullanır. C++ birlikte çalışabilirliği (C++ için tipik bir biçimde), varsayılan olarak en iyi performans sağlar, ve Programcı bu davranışı güvenli ve uygun olduğu durumlarda ele almak için sorumlu olduğu anlamına gelir.

C++ birlikte çalışması, bu nedenle veri hazırlama açıkça girilmesi gerekir, ancak avantajı Programcı uygun, veri yapısını nedir ve nasıl kullanılacak olan karar vermek ücretsiz olmasıdır gerektirir. Ayrıca, P/Invoke veri hazırlama davranışını konumunda bir dereceye değiştirilebilir ancak C++ birlikte çalışması veri hazırlama çağrı çağrısı bazında özelleştirilmesine olanak sağlar. Bu, P/Invoke ile mümkün değildir.

C++ birlikte çalışması hakkında daha fazla bilgi için bkz: [C++ Çalışabilirliği kullanma (örtük PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md).

## <a name="see-also"></a>Ayrıca bkz.

[Karışık (Yerel ve Yönetilen) Derlemeler](../dotnet/mixed-native-and-managed-assemblies.md)
