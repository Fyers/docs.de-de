---
title: IMetaDataTables::GetRow-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetRow
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetRow
helpviewer_keywords:
- IMetaDataTables::GetRow method [.NET Framework metadata]
- GetRow method [.NET Framework metadata]
ms.assetid: a7408d51-0bce-45a2-b58f-da4660bbc039
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d24dbcbdd8b0ed0736f7b59564cf72dffaa5a8f8
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/08/2018
ms.locfileid: "44196711"
---
# <a name="imetadatatablesgetrow-method"></a>IMetaDataTables::GetRow-Methode
Ruft die Zeile am angegebenen Zeilenindex, in der Tabelle auf den Index der angegebenen Tabelle.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetRow (   
    [in]  ULONG   ixTbl,  
    [in]  ULONG   rid,  
    [out] void    **ppRow  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `ixTbl`  
 [in] Der Index des in der Tabelle, aus der die Zeile abgerufen werden.  
  
 `rid`  
 [in] Der Index der abzurufenden Zeile.  
  
 `ppRow`  
 [out] Ein Zeiger auf einen Zeiger auf die Zeile.  
  
## <a name="remarks"></a>Hinweise  
 Die Verwendung von dieser Methode wird nicht empfohlen, da es keine konsistente Ergebnisse zurückgibt. Informationen über den GUID-Tabelle finden Sie unter der Common Language Infrastructure (CLI)-Dokumentation, besonders in "Partition II: Metadata Definition and Semantics". Die Dokumentation ist online verfügbar. Sie finden sie unter [ECMA C# and Common Language Infrastructure Standards (Standards von ECMA C# und Common Language Infrastructure)](https://go.microsoft.com/fwlink/?LinkID=99212) auf MSDN und [Standard ECMA-335 - Common Language Infrastructure (CLI) (Standard ECMA-335 – Common Language Infrastructure (CLI))](https://go.microsoft.com/fwlink/?LinkID=65552) auf der Ecma International-Website.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [IMetaDataTables-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [IMetaDataTables2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
