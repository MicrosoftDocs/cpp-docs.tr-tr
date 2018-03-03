---
title: "Bağımsız değişken tanımı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- envp argument
- main function, syntax
- arguments [C++], for main function
- argv argument
- argc argument
ms.assetid: 91c2cbe3-9aca-4277-afa1-6137eb8fb704
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f3a9597ca8807c8ac1a3182b3daa1891a195c39c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="argument-description"></a>Bağımsız Değişken Tanımı
`argc` Parametresinde **ana** ve **wmain** işlevleri kaç tane bağımsız değişkenleri komut satırından programa geçirilen belirten bir tamsayı değil. Program adı değerini bağımsız değişken olarak kabul edilir beri `argc` en az biri.  
  
## <a name="remarks"></a>Açıklamalar  
 `argv` Parametresi null ile sonlandırılmış dizeler program değişkenleri temsil eden işaretçiler bir dizisidir. Her öğe için bağımsız değişken bir dize gösterimini dizi noktalarının geçirilen **ana** (veya **wmain**). (Dizileri hakkında daha fazla bilgi için bkz: [dizi bildirimleri](../c-language/array-declarations.md).) `argv` Parametre türü işaretçileri dizisi olarak ya da bildirilebilir `char` (`char *argv[]`) veya işaretçi türü için bir işaretçi olarak `char` (`char **argv`). İçin **wmain**, `argv` parametre türü işaretçileri dizisi olarak ya da bildirilebilir `wchar_t` (`wchar_t *argv[]`) veya işaretçi türü için bir işaretçi olarak `wchar_t` (`wchar_t **argv`).  
  
 Kural tarafından `argv` **[0]** ile program çağrılır komutu.  Ancak, bir işlemi kullanarak oluşturma olası [CreateProcess](http://msdn.microsoft.com/library/windows/desktop/ms682425) ve birinci ve ikinci bağımsız kullanıyorsanız (`lpApplicationName` ve `lpCommandLine`), `argv` **[0]** olmayabilir yürütülebilir dosya adı; kullanmak [GetModuleFileName](http://msdn.microsoft.com/library/windows/desktop/ms683197) yürütülebilir dosya adı alınamadı.  
  
 Son işaretçisi (`argv[argc]`) olan **NULL**. (Bkz [getenv](../c-runtime-library/reference/getenv-wgetenv.md) içinde *çalışma zamanı kitaplığı başvurusu* ortam değişkeni bilgisi almak için alternatif bir yöntem için.)  
  
 **Microsoft özel**  
  
 `envp` Parametresi bir işaretçidir kullanıcının ortam değişkenlerini ayarlama değerlerini temsil eden bir null ile sonlandırılmış dizeler dizisi. `envp` Parametresi, bir dizi işaretçiler olarak bildirilebilir `char` (`char *envp[]`) veya işaretçileri gösteren bir işaretçi olarak `char` (`char **envp`). İçinde bir **wmain** işlevi, `envp` parametresi, bir dizi işaretçiler olarak bildirilebilir `wchar_t` (`wchar_t *envp[]`) veya işaretçileri gösteren bir işaretçi olarak `wchar_t` (`wchar_t **envp`). Dizinin sonuna tarafından belirtilen bir **NULL** \*işaretçi. Ortam bloğu geçirilen Not **ana** veya **wmain** geçerli ortamda "dondurulmuş" bir kopyasıdır. Ortam _ çağrısıyla daha sonra değiştirirseniz**putenv** veya `_wputenv`, geçerli ortamı (tarafından döndürülen `getenv` / `_wgetenv` ve `_environ` veya `_wenviron` değişkenler) değiştirir, ancak tarafından için blok işaret `envp` değişmez. `envp` ANSI C, ancak içinde değil C++ uyumlu bir parametredir.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [main İşlevi ve Program Yürütme](../c-language/main-function-and-program-execution.md)