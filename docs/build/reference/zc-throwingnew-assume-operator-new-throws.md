---
title: "/ZC:throwingNew (varsay işleci yeni atar) | Microsoft Docs"
ms.custom: 
ms.date: 12/13/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- throwingNew
- /Zc:throwingNew
dev_langs: C++
helpviewer_keywords:
- -Zc compiler options (C++)
- throwingNew
- Assume operator new Throws
- /Zc compiler options (C++)
- Zc compiler options (C++)
ms.assetid: 20ff0101-9677-4d83-8c7b-8ec9ca49f04f
caps.latest.revision: "1"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: bc784af1c23576ff68c8be8b4b400cd10cc8b0e2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="zcthrowingnew-assume-operator-new-throws"></a>/ZC:throwingNew (varsay işleci yeni atar)  
Zaman `/Zc:throwingNew` seçeneği belirtildiğinde, derleyici çağrıları iyileştirir `operator new` dönüş null işaretçi denetler atlanacak. Bu seçenek tüm uygulamaları bağlı varsaymak derleyici söyler `operator new` ve özel allocators C++ standardına uygun ayırma hatası atar. Visual Studio'da varsayılan olarak, derleyici zor null denetimlerinin oluşturur (`/Zc:throwingNew-`) için bu çağrı, kullanıcıların bir atma olmayan uygulamasıyla bağlayabilirsiniz çünkü `operator new` veya null işaretçiler döndüren özel ayırıcısı yordamları yazma.  
  
## <a name="syntax"></a>Sözdizimi  
  
`/Zc:throwingNew`[`-`]  
  
## <a name="remarks"></a>Açıklamalar  
  
C ++ 98 ISO itibaren standart belirtmiş varsayılan [new işleci](../../standard-library/new-operators.md#op_new) oluşturur `std::bad_alloc` bellek ayırma başarısız olduğunda. Visual Studio 6.0 kadar Visual C++ sürümü null bir işaretçi bir ayırma hatası döndürdü. Visual Studio 2002'den itibaren `operator new` standardına uygun ve hatası oluşturur. Eski ayırma stili kullanan kodu desteklemek için Visual Studio linkable bir uygulamasını sağlar `operator new` içinde *nothrownew.obj* , bir null işaretçinin hatası döndürür. Varsayılan olarak, derleyici hatası hemen bir çökmesine neden bu eski stil allocators önlemek için savunma null denetimlerinin de oluşturur. `/Zc:throwingNew` Seçenek bu null denetimlerinin bırakmayı derleyici söyler, tüm bellek bağlı varsayımına allocators standardına uygun. Bu açık olmayan atma için uygulanmaz `operator new` ek bir parametre türü kullanılarak bildirilen aşırı `std::nothrow_t` ve açık bir `noexcept` belirtimi.  
  
Kavramsal olarak, bir nesne üzerinde boş deposu oluşturmak için kendi bellek ayıramadı kod derleyici oluşturur ve bellek başlatmak için kendi Oluşturucu çağrılamıyor. Visual C++ Derleyici, normal olarak bu kodu için DSCP, atma olmayan bir ayırıcı bağlı değilse bildiremez olduğundan, varsayılan olarak, aynı zamanda Oluşturucusu çağırmadan önce null denetimi oluşturur. Bu, bir null işaretçinin engeller atma olmayan bir ayırma başarısız olursa Oluşturucusu çağrısında başvuru. Çoğu durumda, bu denetimleri gereksiz, çünkü varsayılan `operator new` allocators throw null işaretçiler döndüren yerine. Denetimleri de talihsiz yan etkileri vardır. Kod boyutu Şişir, bunlar şube göstergesi olduğu bölgesini doldurmak ve diğer yararlı derleyici iyileştirmelerini devirtualization veya başlatılmamış nesne dışında const yayma gibi engelle. Bağlanan destek koduna denetimleri mevcut *nothrownew.obj* veya özel uyumsuz `operator new` uygulamaları. Uyumsuz kullanmıyorsanız `operator new`, kullandığınız öneririz `/Zc:throwingNew` kodunuzu en iyi duruma getirme.  
  
Bağlama zamanı kodu oluşturma (LTCG) kullanarak derleme yaparsanız belirtmeniz gerekmez `/Zc:throwingNew`. Kodunuzu LTCG kullanarak derlendiğinde derleyici varsa algılayabilir varsayılan olarak uyumsuz `operator new` uygulama kullanılır. Bu durumda, derleyici null denetimlerinin otomatik olarak bırakır. Bağlayıcı arar `/ThrowingNew` bildirmek için bayrağı varsa uygulanması `operator new` uyumsuz olduğu. Bu yönerge, özel işleci yeni uygulamanız için kaynak ekleyerek bu bayrak bağlayıcı belirtebilirsiniz:  
  
```cpp  
#pragma comment(linker, "/ThrowingNew")  
```  
  
Visual c++ uyumluluk sorunları hakkında daha fazla bilgi için bkz: [standart dışı davranış](../../cpp/nonstandard-behavior.md).  
  
## <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
2.  Gelen **yapılandırmaları** açılır menü, seçin **tüm yapılandırmaları**.  
3.  Seçin **yapılandırma özellikleri**, **C/C++**, **komut satırı** özellik sayfası.  
4.  Değiştirme **ek seçenekler** eklenecek özellik `/Zc:throwingNew` veya `/Zc:throwingNew-` ve ardından **Tamam**.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
[Derleyici Seçenekleri](../../build/reference/compiler-options.md)  
[Derleyici seçeneklerini ayarlama](../../build/reference/setting-compiler-options.md)  
[/ZC (Uyumluluk)](../../build/reference/zc-conformance.md)  
[noexcept (C++)](../../cpp/noexcept-cpp.md)  
[Özel durum belirtimleri (throw) (C++)](../../cpp/exception-specifications-throw-cpp.md)  
[(özel) Sonlandır](../../standard-library/exception-functions.md#terminate)  
