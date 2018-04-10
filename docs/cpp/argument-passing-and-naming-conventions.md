---
title: Bağımsız değişkeni geçirme ve adlandırma kuralları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-language
ms.tgt_pltfrm: ''
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- argument passing [C++], conventions
- arguments [C++], widening
- coding conventions, arguments
- arguments [C++], passing
- registers, return values
- thiscall keyword [C++]
- naming conventions [C++], arguments
- arguments [C++], naming
- passing arguments [C++], conventions
- conventions [C++], argument names
ms.assetid: de468979-eab8-4158-90c5-c198932f93b9
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d57afcd518455ffb836e4d724a68b7d3e5682d6c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="argument-passing-and-naming-conventions"></a>Bağımsız Değişkeni Geçirme ve Adlandırma Kuralları
**Microsoft özel**  
  
 Visual C++ Derleyicileri bağımsız değişkenleri geçirme için kuralları belirtin ve işlevleri ve arayanlar arasında dönüş değerleri olanak sağlar. Tüm kuralları tüm desteklenen platformlarda kullanılabilir ve platforma özgü uygulamaları bazı kuralları kullanır. Çoğu durumda, anahtar sözcükleri veya desteklenmeyen bir kural belirli bir platformda belirtin derleyici anahtarları dikkate alınmaz ve platform varsayılan kuralı kullanılır.  
  
 X86 üzerinde bunlar geçirildiğinde, plaftorms, tüm bağımsız değişkenler için 32 bit devam. Dönüş değerleri de 32 bit devam ve EDX:EAX kayıt çiftinin döndürülen 8-bayt yapıları dışında EAX kayıt döndürdü. Daha büyük yapıları döndürülür EAX kayıttaki işaretçiler olarak gizli yapıları döndürür. Yığına, sağdan sola parametreleri gönderilir. Pod'ları olmayan yapıları Yazmaçları döndürülmedi.  
  
 Giriş derleyici oluşturur ve işlevinde kullandıysanız kaydedip ESI, EDI, EBX ve EBP geri yüklemek için bitiş kodu kaydeder.  
  
> [!NOTE]
>  Bir yapı, UNION ya da sınıf değere göre bir işleve döndürüldüğünde, türündeki tüm tanımları aynı olması gerekir, programın çalışma zamanında başka başarısız olabilir.  
  
 Kendi işlev giriş ve bitiş kodu tanımlama hakkında daha fazla bilgi için bkz: [Naked işlevi çağrıları](../cpp/naked-function-calls.md).  
  
 Varsayılan hakkında bilgi için kuralları hedefleri x64 platformları görmek kodda çağırma [x64 genel bakış çağırma kuralları](../build/overview-of-x64-calling-conventions.md). Kuralı sorunları ARM platformları hedefleyen kodu çağırma hakkında daha fazla bilgi için bkz: [genel Visual C++ ARM geçiş sorunları](../build/common-visual-cpp-arm-migration-issues.md).  
  
 Aşağıdaki çağırma kurallarını Visual C/C++ derleyicisi tarafından desteklenir.  
  
|Anahtar sözcüğü|Yığın temizleme|Parametre geçirme|  
|-------------|-------------------|-----------------------|  
|[__cdecl](../cpp/cdecl.md)|Arayan|Parametrelerini yığına ters sırada (sağdan sola) gönderir.|  
|[__clrcall](../cpp/clrcall.md)|yok|Parametreleri CLR ifade yığını sırasına (soldan sağa) üzerine yükleyin.|  
|[__stdcall](../cpp/stdcall.md)|Aranan|Parametrelerini yığına ters sırada (sağdan sola) gönderir.|  
|[__fastcall](../cpp/fastcall.md)|Aranan|Ardından yığına kaydeder depolanır|  
|[__thiscall](../cpp/thiscall.md)|Aranan|Yığına; **bu** ECX içinde depolanan işaretçi|  
|[__vectorcall](../cpp/vectorcall.md)|Aranan|Ardından ters sırada (sağdan sola) yığına kaydeder depolanır|  
  
 İlgili bilgi için bkz: [artık kullanılmayan çağırma kuralları](../cpp/obsolete-calling-conventions.md).  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çağırma Kuralları](../cpp/calling-conventions.md)