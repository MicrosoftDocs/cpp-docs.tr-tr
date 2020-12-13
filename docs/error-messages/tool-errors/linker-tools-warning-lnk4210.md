---
description: 'Daha fazla bilgi edinin: bağlayıcı araçları uyarısı LNK4210'
title: Bağlayıcı Araçları Uyarısı LNK4210
ms.date: 11/04/2016
f1_keywords:
- LNK4210
helpviewer_keywords:
- LNK4210
ms.assetid: db48cff8-a2be-4a77-8d03-552b42c228fa
ms.openlocfilehash: 7634952df026dc664aed2a2f9625a7380b3a38b4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97150611"
---
# <a name="linker-tools-warning-lnk4210"></a>Bağlayıcı Araçları Uyarısı LNK4210

> bölüm *bölümü* var; işlenmemiş statik başlatıcılar veya sonlandırıcılar olabilir

## <a name="remarks"></a>Açıklamalar

Bazı kodlar statik başlatıcılar veya sonlandırıcılar sunmuştur, ancak VCRuntime kitaplığı başlangıç kodu veya eşdeğeri (statik başlatıcıları veya Sonlandırıcıların çalıştırılması gereken) uygulama başladığında çalıştırılmıyor. Statik başlatıcılar veya sonlandırıcılar gerektiren kod örnekleri aşağıda verilmiştir:

- Oluşturucu, yıkıcı veya sanal işlev tablosu ile genel sınıf değişkeni.

- Bir derleme zamanı sabiti ile başlatılan genel değişken.

Bu sorunu gidermek için aşağıdakilerden birini deneyin:

- Statik başlatıcılarla tüm kodu kaldırın.

- [/NOENTRY](../../build/reference/noentry-no-entry-point.md)kullanmayın. /NOENTRY kaldırıldıktan sonra bağlayıcı komut satırınızdan [/nodefaultlib](../../build/reference/nodefaultlib-ignore-libraries.md) ' i de kaldırmanız gerekebilir.

- Derlemeniz/MT kullanıyorsa, bağlayıcı komut satırına Libcmt. lib, libvcruntime. lib ve libucrt. lib ekleyin. Derlemeniz/MTd kullanıyorsa, LIBCMTD. lib, vcruntimed. lib ve libucrtd. lib ekleyin.

- /Clr: saf derlemeden/clr 'e geçiş yaparken, [/Entry](../../build/reference/entry-entry-point-symbol.md) seçeneğini bağlayıcı satırından kaldırın. Bu, CRT başlatmayı sağlar ve uygulama başlangıcında statik başlatıcıların yürütülmesini sağlar. **/Clr: Pure** derleyici seçeneği visual Studio 2015 ' de kullanımdan kaldırılmıştır ve visual Studio 2017 ' de desteklenmez.

[/GS](../../build/reference/gs-buffer-security-check.md) derleyici seçeneği, işlevinin başlatılmasını gerektirir `__security_init_cookie` . Bu başlatma, içinde çalışan VCRuntime kitaplığı başlangıç kodunda varsayılan olarak sağlanır `_DllMainCRTStartup` .

- Projeniz/ENTRY kullanılarak oluşturulmuş ise ve/ENTRY dışında bir işlev geçirtiyse, `_DllMainCRTStartup` IŞLEVIN `_CRT_INIT` CRT 'yi başlatmak için çağrısı gerekir. DLL 'niz/GS kullanıyorsa, statik başlatıcılar gerektiriyorsa veya MFC veya ATL kodu bağlamında çağrılırsa bu çağrı tek başına yeterli değildir. Daha fazla bilgi için bkz. [DLL 'ler ve Visual C++ çalışma zamanı kitaplığı davranışı](../../build/run-time-library-behavior.md) .

## <a name="see-also"></a>Ayrıca bkz.

- [Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/linking.md)
