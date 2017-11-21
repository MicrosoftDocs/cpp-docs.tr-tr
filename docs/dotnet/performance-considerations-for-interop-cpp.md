---
title: "Birlikte çalışabilirlik için başarım düşünceleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- /clr compiler option [C++], interop performance considerations
- platform invoke [C++], interoperability
- interop [C++], performance consideraitons
- mixed assemblies [C++], performance considerations
- interoperability [C++], performance considerations
ms.assetid: bb9a282e-c3f8-40eb-a2fa-45d80d578932
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: fc5e22350036b9f13ee8800cad8394133ba7abd1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="performance-considerations-for-interop-c"></a>Birlikte Çalışabilirlik için Başarım Düşünceleri (C++)
Bu konu, yönetilen ve yönetilmeyen birlikte çalışma geçişleri çalışma zamanı performans üzerindeki etkisini azaltmak için yönergeler sağlar.  
  
 Visual C++, Visual Basic ve C# (P/Invoke) gibi diğer .NET dilleri ile aynı birlikte çalışabilirlik düzeneklerini destekler, ancak ayrıca Visual C++ (C++ birlikte çalışması) özgü birlikte çalışma desteği sağlar. Performans açısından kritik uygulamalar için her birlikte çalışma teknik performans etkilerini anlamak önemlidir.  
  
 Kullanılan birlikte çalışma teknik bağımsız olarak dönüştürücüler, denen özel geçiş dizileri bir yönetilmeyen işlevi tersi yönetilen bir işlev çağrıları her zaman gereklidir. Bu dönüştürücüler Visual C++ derleyicisi tarafından otomatik olarak eklenir, ancak üst üste, bu geçişleri performans açısından pahalı olabileceğini göz önünde bulundurmanız önemlidir.  
  
## <a name="reducing-transitions"></a>Geçişleri azaltma  
 Önlemenize veya birlikte çalışma dönüştürücüler maliyetini azaltmak için bir yönetilen ve yönetilmeyen geçişleri en aza indirmek söz konusu arabirimleri yeniden düzenlemeniz yoldur. Önemli ölçüde performans iyileştirmeleri, yönetilen ve yönetilmeyen sınırından sık çağrıları ilgili olanlardır chatty arabirimleri hedefleyerek yapılabilir. Sıkı bir döngüde yönetilmeyen işlev çağıran bir yönetilen Örneğin, iyi bir aday yeniden düzenleme için işlevdir. Döngü yönetilmeyen tarafa taşıdıysanız veya yönetilen bir alternatif, yönetilmeyen çağrı oluşturulur (belki yönetilen tarafta queuing veriler ve ardından aynı anda döngüden sonra yönetilmeyen API için hazırlama), geçiş sayısı olabilir oturum azaltılmış ificantly.  
  
## <a name="pinvoke-vs-c-interop"></a>P/Invoke vs. C++ Birlikte Çalışma  
 Visual Basic ve C# gibi .NET dilleri için yerel bileşenleriyle birlikte önceden belirlenen P/Invoke yöntemdir. P/Invoke .NET Framework tarafından desteklenmediği için Visual C++, de destekler, ancak Visual C++, C++ birlikte çalışması adlandırılan kendi birlikte çalışabilirlik desteği de sağlar. C++ birlikte çalışabilirliği P/Invoke tür kullanımı uyumlu olmadığından P/Invoke tercih edilir. Sonuç olarak, öncelikle çalışma zamanında rapor hata ancak C++ birlikte çalışabilirliği de P/Invoke performans avantajları vardır.  
  
 Her iki tekniği birkaç şeyin yönetilen bir işlev yönetilmeyen işlev çağırdığında yapılmasını gerektirir:  
  
-   İşlev çağrısı bağımsız değişkenleri CLR yerel türleri için hazırlanırlar.  
  
-   Yönetilmeyen bir dönüştürücü yürütülür.  
  
-   Yönetilmeyen işlevi (bağımsız değişkenler yerel sürümleri kullanarak) adı verilir.  
  
-   Yönetilen için yönetilmeyen bir dönüştürücü yürütülür.  
  
-   Dönüş türü ve tüm "out" veya "ın, out" bağımsız değişkenleri CLR'den CLR türleri için yerel.  
  
 Yönetilen ve yönetilmeyen dönüştürücüler çalışması birlikte çalışması için gerekli olan, ancak söz konusu veri türlerine, işlev imzası ve verilerin nasıl kullanılacağını gerekli verileri hazırlama bağlıdır.  
  
 C++ birlikte çalışabilirliği tarafından gerçekleştirilen veri hazırlama basit olası formdur: parametreleri yalnızca yönetilen ve yönetilmeyen sınır Bitsel bir şekilde; arasında kopyalanır hiçbir dönüştürme hiç gerçekleştirilir. P/Invoke için bu yalnızca tüm parametreleri basit ise geçerlidir blittable türleri. Aksi takdirde, P/Invoke her yönetilen parametreyi uygun yerel bir tür için dönüştürmek için güçlü adımlar gerçekleştirir ve tersi bağımsız değişkenler "dışı" işaretlenmişse veya "ın, out".  
  
 Diğer bir deyişle, C++ birlikte çalışabilirliği veri hazırlama olası en hızlı yöntemi kullanır, ancak P/Invoke en güçlü yöntemi kullanır. C++ birlikte çalışabilirliği (C++ için normal bir şekilde) varsayılan olarak en iyi performans sağlar ve Programcı Bu davranış güvenli veya uygun olduğu durumlarda adreslemek için sorumlu olduğu anlamına gelir.  
  
 C++ birlikte çalışması, bu nedenle verileri hazırlama açıkça sağlanması gerekir, ancak avantajı Programcı uygun, veri yapısı nedir ve nasıl kullanılacak olan karar vermek ücretsiz olmasıdır gerektirir. Ayrıca, P/Invoke verileri hazırlama davranışı konumundaki bir dereceye özelleştirilmiş değiştirilebilir rağmen C++ birlikte çalışabilirliği veri bir çağrı tarafından çağrı temelinde özelleştirilmek üzere hazırlama sağlar. Bu P/Invoke ile mümkün değildir.  
  
 C++ birlikte çalışma hakkında daha fazla bilgi için bkz: [C++ Çalışabilirliği kullanarak (örtük PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Karışık (yerel ve yönetilen) derlemeler](../dotnet/mixed-native-and-managed-assemblies.md)