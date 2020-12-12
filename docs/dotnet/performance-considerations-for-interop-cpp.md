---
description: 'Daha fazla bilgi edinin: birlikte çalışabilirlik için performans konuları (C++)'
title: Birlikte Çalışabilirlik için Başarım Düşünceleri (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- /clr compiler option [C++], interop performance considerations
- platform invoke [C++], interoperability
- interop [C++], performance consideraitons
- mixed assemblies [C++], performance considerations
- interoperability [C++], performance considerations
ms.assetid: bb9a282e-c3f8-40eb-a2fa-45d80d578932
ms.openlocfilehash: 29723f0ea5c7b745100ab4c7abb7f59abce47db6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97255567"
---
# <a name="performance-considerations-for-interop-c"></a>Birlikte Çalışabilirlik için Başarım Düşünceleri (C++)

Bu konu, yönetilen/yönetilmeyen birlikte çalışma geçişlerinin çalışma zamanı performansına etkisini azaltmak için yönergeler sağlar.

Visual C++, Visual Basic ve C# (P/Invoke) gibi diğer .NET dilleri ile aynı birlikte çalışabilirlik mekanizmalarını destekler, ancak aynı zamanda Visual C++ (C++ birlikte çalışma) ile birlikte çalışabilirlik desteği de sağlar. Performans açısından kritik uygulamalar için, her birlikte çalışma tekniğinin performans etkilerini anlamak önemlidir.

Kullanılan birlikte çalışma tekniğinden bağımsız olarak, yönetilen bir işlev yönetilmeyen bir işlevi çağırdığında ve tam tersi olduğunda, dönüştürücüler adlı özel geçiş dizileri gereklidir. Bu dönüştürücüler, Microsoft C++ derleyicisi tarafından otomatik olarak eklenir, ancak bu geçişlerin performans açısından pahalı olabileceğini göz önünde bulundurmanız önemlidir.

## <a name="reducing-transitions"></a>Geçişleri azaltma

Birlikte çalışabilirlik dönüştürücüler maliyetini önlemenin veya azaltmanın bir yolu, yönetilen/yönetilmeyen geçişleri en aza indirmek için dahil edilen arabirimlerin yeniden düzenlenmesinden biridir. Yönetilen/yönetilmeyen sınır genelinde sık gerçekleştirilen çağrılara sahip olan geveze arabirimlerini hedefleyerek çarpıcı performans iyileştirmeleri yapılabilir. Yönetilmeyen bir işlevi sıkı bir döngüde çağıran yönetilen bir işlev, örneğin, yeniden düzenleme için iyi bir adaydır. Döngü, yönetilmeyen tarafa taşınırsa veya yönetilmeyen çağrıya yönelik yönetilen bir alternatif oluşturulduysa (Belki de yönetilen tarafta verileri sıraya alabilir ve sonra onu döngüden sonra yönetilmeyen API 'ye yeniden sıralama), geçişlerin sayısı önemli ölçüde azaltılabilir.

## <a name="pinvoke-vs-c-interop"></a>P/Invoke ile C++ birlikte çalışabilirliği

Visual Basic ve C# gibi .NET dilleri için, yerel bileşenlerle birlikte çalışmaya yönelik önceden tanımlanmış Yöntem P/Invoke ' dir. P/Invoke .NET Framework tarafından desteklendiğinden, Visual C++ de destekler, ancak Visual C++ C++ birlikte çalışabilirliği olarak adlandırılan kendi birlikte çalışabilirlik desteğini de sağlar. P/Invoke tür kullanımı uyumlu olmadığından, C++ birlikte çalışması P/Invoke üzerinden tercih edilir. Sonuç olarak, hatalar öncelikle çalışma zamanında raporlanır, ancak C++ birlikte çalışabilirliği de P/Invoke üzerinden performans avantajlarına sahiptir.

Her iki teknik de, yönetilen bir işlev yönetilmeyen bir işlevi çağırdığında birkaç şeyin gerçekleşmesi gerekir:

- İşlev çağrısı bağımsız değişkenleri CLR 'den yerel türlere sıralanır.

- Yönetilen-yönetilmeyen bir dönüştürücü yürütülür.

- Yönetilmeyen işlev çağrılır (bağımsız değişkenlerin yerel sürümleri kullanılarak).

- Yönetilmeyenden yönetilene dönüştürücü yürütülür.

- Dönüş türü ve "Out" veya "in, Out" bağımsız değişkenleri yerelden CLR türlerine göre sıralanır.

Yönetilen/yönetilmeyen dönüştürücüler, birlikte çalışma için gereklidir, ancak gereken veri sıralaması, ilgili veri türlerine, işlev imzasına ve verilerin nasıl kullanılacağına bağlıdır.

C++ birlikte çalışması tarafından gerçekleştirilen veri hazırlama mümkün olan en basit biçimdedir: parametreler, yönetilen/yönetilmeyen sınır genelinde bit düzeyinde bir biçimde kopyalanır; hiçbir dönüşüm gerçekleştirilmez. P/Invoke için bu yalnızca tüm parametrelerin basit, blittable türleri olması durumunda geçerlidir. Aksi takdirde, P/Invoke her bir yönetilen parametreyi uygun bir yerel türe dönüştürmek için çok güçlü adımlar gerçekleştirir ve bağımsız değişkenler "Out" veya "ın, Out" olarak işaretlenmişse tam tersi de geçerlidir.

Diğer bir deyişle, C++ birlikte çalışması en hızlı olası veri sıralama yöntemini kullanır, ancak P/Invoke en güçlü yöntemi kullanır. Bu, C++ birlikte çalışabilirliğine (C++ için tipik bir biçimde) varsayılan olarak en iyi performansı sağlar ve bu davranışın güvenli veya uygun olmadığı durumlarda programcı sorumludur.

C++ birlikte çalışması için veri hazırlamayı açık bir şekilde sağlanması gerekir, ancak avantajı, programcının ne kadar uygun olduğuna, verilerin doğasına ve nasıl kullanılacağına karar vermek için ücretsizdir. Ayrıca, P/Invoke veri hazırlama davranışı bir dereceye kadar değiştirilebilir, ancak C++ birlikte çalışması, veri hazırlama sırasında arama temelinde özelleştirilmesine izin verir. Bu, P/Invoke ile mümkün değildir.

C++ birlikte çalışabilirliği hakkında daha fazla bilgi için bkz. [C++ birlikte çalışabilirliği kullanma (örtük PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md).

## <a name="see-also"></a>Ayrıca bkz.

[Karışık (yerel ve yönetilen) derlemeler](../dotnet/mixed-native-and-managed-assemblies.md)
