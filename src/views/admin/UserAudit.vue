<template>
    <div class="userAudit">
        <h3>普通用户</h3>
        <el-table :data="userList"  style="width: 80%">
            <el-table-column prop="id" label="ID" width="180">
            </el-table-column>
            <el-table-column label="姓名" width="180">
            <template slot-scope="scope">
                <el-popover trigger="hover" placement="top">
                <p>姓名: {{ scope.row.name }}</p>
                <p>电话: {{ scope.row.phone }}</p>
        
                <el-tag
                :type="getTap(scope.row)"
                disable-transitions>{{scope.row.status | statusValue}}</el-tag>
            </template>
            </el-table-column>
            <el-table-column label="审核结果">
            <template slot-scope="scope">
                <el-button
                size="mini"
      