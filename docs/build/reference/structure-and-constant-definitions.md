---
title: "Yapı ve sabit tanımları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 1df7cf46-b853-4788-a257-100d5c37997f
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4f77c74ab4b8c72973526007b2496554f5e672ac
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="structure-and-constant-definitions"></a>Yapı ve Sabit Tanımları
Varsayılan Yardımcısı yordamı birkaç yapıdan sırasında özel durumlar kanca işlevleri ile iletişim kurmak için kullanır. Bildirim ve hata değerlerini, bilgi yapıları ve kancaları geçirilen işlevi kanca işaretçi türü şunlardır:  
  
```  
//  
// Delay load import hook notifications  
//  
enum {  
    dliStartProcessing,        // used to bypass or note helper only  
    dliNotePreLoadLibrary,     // called just before LoadLibrary, can  
                               //  override w/ new HMODULE return val  
    dliNotePreGetProcAddress,  // called just before GetProcAddress, can  
                               //  override w/ new FARPROC return value  
    dliFailLoadLib,            // failed to load library, fix it by  
                               //  returning a valid HMODULE  
    dliFailGetProc,            // failed to get proc address, fix it by  
                               //  returning a valid FARPROC  
    dliNoteEndProcessing,      // called after all processing is done, no  
                               //  bypass possible at this point except  
                               //  by longjmp()/throw()/RaiseException.  
    };  
  
typedef struct DelayLoadProc {  
    BOOL                fImportByName;  
    union {  
        LPCSTR          szProcName;  
        DWORD           dwOrdinal;  
        };  
    } DelayLoadProc;  
  
typedef struct DelayLoadInfo {  
    DWORD           cb;         // size of structure  
    PCImgDelayDescr pidd;       // raw form of data (everything is there)  
    FARPROC *       ppfn;       // points to address of function to load  
    LPCSTR          szDll;      // name of dll  
    DelayLoadProc   dlp;        // name or ordinal of procedure  
    HMODULE         hmodCur;    // the hInstance of the library we have loaded  
    FARPROC         pfnCur;     // the actual function that will be called  
    DWORD           dwLastError;// error received (if an error notification)  
    } DelayLoadInfo, * PDelayLoadInfo;  
  
typedef FARPROC (WINAPI *PfnDliHook)(  
    unsigned        dliNotify,  
    PDelayLoadInfo  pdli  
    );  
  
typedef struct ImgDelayDescr {  
    DWORD        grAttrs;        // attributes  
    RVA          rvaDLLName;     // RVA to dll name  
    RVA          rvaHmod;        // RVA of module handle  
    RVA          rvaIAT;         // RVA of the IAT  
    RVA          rvaINT;         // RVA of the INT  
    RVA          rvaBoundIAT;    // RVA of the optional bound IAT  
    RVA          rvaUnloadIAT;   // RVA of optional copy of original IAT  
    DWORD        dwTimeStamp;    // 0 if not bound,  
                                 // O.W. date/time stamp of DLL bound to (Old BIND)  
    } ImgDelayDescr, * PImgDelayDescr;  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yardımcı İşlevini Anlama](../../build/reference/understanding-the-helper-function.md)