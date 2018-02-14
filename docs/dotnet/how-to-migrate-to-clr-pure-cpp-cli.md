---
title: "Nasıl yapılır: geçirmek için - clr: pure (C + +/ CLI) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- /clr compiler option [C++], migrating to /clr:pure
- migration [C++], pure MSIL
- pure MSIL [C++], porting to
ms.assetid: 5ffb1184-2095-4ade-84aa-4fa6324bc764
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: b8d49ee233167c02570408ba091c2a99b78487d5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-migrate-to-clrpure-ccli"></a>Nasıl yapılır: /clr:pure'a Geçiş (C++/CLI)
Bu konuda kullanarak saf MSIL geçirilirken çıkabilecek sorunları ele alınmıştır **/CLR: pure** (bkz [/CLR (ortak dil çalışma zamanı derlemesi)](../build/reference/clr-common-language-runtime-compilation.md) daha fazla bilgi için). Bu konu geçirilen kodun şu anda kullanılarak karışık derleme olarak derlendiğini varsayar **/CLR** saf MSIL yönetilmeyen koddan geçiş yolunun doğrudan olmaması seçeneğiyle. Yönetilmeyen kod için bkz: [nasıl yapılır: pure'a Geçiş](../dotnet/how-to-migrate-to-clr.md) saf MSIL geçirmeyi denemeden önce.  
  
## <a name="basic-changes"></a>Temel değişiklikler  
 MSIL içinde açıklanamayan işlevleri içeren kod derleme engelleyecek şekilde saf MSIL MSIL yönergeleri, oluşur. Bu dışında çağırma kurallarını kullanarak tanımlanan işlevleri içerir [__clrcall](../cpp/clrcall.md). (__Clrcall olmayan işlevler bir saf MSIL bileşeni çağrılır, ancak tanımlı değil.)  
  
 Çalışma zamanı hataları emin olmak için C4412 uyarılarını etkinleştirmeniz gerekir. Ekleyerek C4412'yi etkinleştirin `#pragma warning (default : 4412)` ile derleme her derlenecek için **/CLR: pure** ve C++ türleri için ve geçen (**/CLR)** veya yerel kod. Bkz: [Derleyici Uyarısı (Düzey 2) C4412'yi](../error-messages/compiler-warnings/compiler-warning-level-2-c4412.md) daha fazla bilgi için.  
  
## <a name="architectural-considerations"></a>Mimari dikkat edilecek noktalar  
 Saf MSIL derlemeleri listelenen sınırlamaları bazıları [saf ve doğrulanabilen kod (C + +/ CLI)](../dotnet/pure-and-verifiable-code-cpp-cli.md) uygulama tasarımınızı ve geçiş stratejisi üst düzey etkiler. Özellikle, karışık derlemelerin aksine, saf MSIL derlemeleri yönetilmeyen modüllerle tam uyumluluk keyfini yok.  
  
 Saf MSIL derlemeleri yönetilmeyen işlevleri çağırabilir ancak yönetilmeyen işlevler tarafından çağrılamaz. Sonuç olarak, saf MSIL yönetilmeyen işlevler tarafından kullanılan sunucu kodu olandan yönetilmeyen işlevleri kullanan istemci kodu için daha iyi bir adaydır. Saf MSIL derlemesinde bulunan işlevselliği yönetilmeyen işlevler tarafından kullanılacak ise, karma bir derleme bir arabirim katmanı kullanılmalıdır.  
  
 Bu kitaplıklar bu sürümde desteklenmez ATL veya MFC kullanan uygulamalar saf MSIL, geçiş için iyi bir aday değildir. Benzer şekilde, [!INCLUDE[winsdkshort](../atl-mfc-shared/reference/includes/winsdkshort_md.md)] altında derleme değil üstbilgi dosyaları içeren **/CLR: pure**.  
  
 Saf MSIL derlemeleri yönetilmeyen işlevleri çağırabilir olsa da, bu özellik basit C stili işlevleri sınırlıdır. COM arabirimi ya da saf MSIL ve yönetilmeyen bileşenleri arasında bir arabirim olarak davranıp karışık bir derleme açığa yönetilmeyen işlevselliği gerektirecek şekilde daha karmaşık yönetilmeyen API kullanımı olasıdır. Karışık derleme katmanı kullanarak, örneğin, geri arama işlevleri almayan yönetilmeyen işlevleri saf derleme bir geri çağırma olarak kullanmak üzere yerel çağrılabilir işlev sağlayamaz olarak kullanılmak üzere tek bir yoludur.  
  
## <a name="application-domains-and-calling-conventions"></a>Uygulama etki alanları ve çağırma kuralları  
 Mümkün olsa saf MSIL derlemeleri yönetilmeyen işlevselliği, İşlevler kullanma ve statik veriler farklı işlenir. Saf derlemelerde işlevleri ile uygulanan [__clrcall](../cpp/clrcall.md) kuralı ve statik verileri çağırma olduğu saklı uygulama başına etki alanı. Bu kullanacağınız yönetilmeyen ve karışık derlemeler için varsayılandan farklı [__cdecl](../cpp/cdecl.md) işlevlerini çağırma ve işlem başına temelinde statik verileri depolar.  
  
 Saf MSIL (ve/CLR: safe ile derlenmiş doğrulanabilen kod) bağlamında bu varsayılan saydam olarak [__clrcall](../cpp/clrcall.md) varsayılan çağırma CLR olduğunu ve uygulama etki alanları statik yerel kapsamını ve .NET uygulamalarında genel veriler. Ancak, yönetilmeyen veya karışık bileşenleriyle arabirim, İşlevler ve genel veriler farklı işlenmesi sorunlara neden olabilir.  
  
 Örneğin, bir yönetilmeyen veya karışık DLL işlevleri çağırmak için saf MSIL bileşeni ise, DLL üstbilgi dosyası saf derlemeyi derlemek için kullanılır. Üst bilgisindeki her işlev için çağırma kuralı açıkça aksi belirtilmedikçe, ancak bunlar tüm olmasını varsayılacak [__clrcall](../cpp/clrcall.md). İle uygulanan bu işlevler büyük olasılıkla gibi bu daha sonra çalışma zamanı hatalarına neden olur [__cdecl](../cpp/cdecl.md) kuralı. Yönetilmeyen başlık dosyasındaki işlevler açıkça olarak işaretlenebilir [__cdecl](../cpp/cdecl.md), veya tüm DLL kaynak kodu derlenmelidir **/CLR: pure**.  
  
 İşlev işaretçileri benzer şekilde, işaret varsayılır [__clrcall](../cpp/clrcall.md) altında işlevleri **/CLR: pure** derleme. Bunlar çok açıkça doğru Çağırma ile Açıklama eklenmelidir.  
  
 Daha fazla bilgi için bkz: [uygulama etki alanları ve Visual C++](../dotnet/application-domains-and-visual-cpp.md).  
  
## <a name="linking-limitations"></a>Bağlama Sınırlamaları  
 Depolama kapsamı ve çağırma kuralları farklı olduğundan Visual C++ bağlayıcı karışık ve saf OBJ dosyaları bağlamak çalışmaz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Saf ve Doğrulanabilen Kod (C++/CLI)](../dotnet/pure-and-verifiable-code-cpp-cli.md)