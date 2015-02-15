package com.example.toeyieie.app_test;

import android.app.ActionBar;
import android.app.FragmentTransaction;
import android.os.Bundle;
import android.support.v4.app.Fragment;
import android.support.v4.app.FragmentActivity;
import android.support.v4.app.FragmentManager;
import android.support.v4.app.FragmentPagerAdapter;
import android.support.v4.view.ViewPager;
import android.view.LayoutInflater;
import android.view.View;
import android.view.ViewGroup;

/**
 * Created by toey on 15/2/2558.
 */
public class mainfragment extends FragmentActivity implements ActionBar.TabListener{

    AppSectionPageAdapter mAppSectionPageAdapter;
    ViewPager mViewPager;
    public void onCreate(Bundle savedInstanceStage){
        super.onCreate(savedInstanceStage);
        setContentView(R.layout.fragmentlayout);

        mAppSectionPageAdapter = new AppSectionPageAdapter (getSupportFragmentManager());

        final ActionBar actionBar = getActionBar();
        actionBar.setNavigationMode(ActionBar.NAVIGATION_MODE_TABS);

        actionBar.setHomeButtonEnabled(false);


        mViewPager = (ViewPager) findViewById(R.id.pager);
        mViewPager.setAdapter(mAppSectionPageAdapter);
        mViewPager.setOnPageChangeListener(new ViewPager.SimpleOnPageChangeListener() {
            @Override
            public void onPageSelected(int position) {
                actionBar.setSelectedNavigationItem(position);
            }
        });
        for (int i = 0 ; i<mAppSectionPageAdapter.getCount();i++){
            actionBar.addTab(actionBar.newTab()
                    .setText(mAppSectionPageAdapter.getPageTitle(i))
                    .setTabListener(this));
        }
    }
    @Override
    public void onTabSelected(ActionBar.Tab tab, FragmentTransaction ft) {
        mViewPager.setCurrentItem(tab.getPosition());
    }

    @Override
    public void onTabUnselected(ActionBar.Tab tab, FragmentTransaction ft) {

    }

    @Override
    public void onTabReselected(ActionBar.Tab tab, FragmentTransaction ft) {

    }

    private class AppSectionPageAdapter extends FragmentPagerAdapter {
        public AppSectionPageAdapter(FragmentManager fm) {
            super(fm);
        }

        @Override
        public Fragment getItem(int i) {
            switch (i){

                case 0:
                    Fragment fragment = new searchpage();
                    Bundle args = new Bundle();
                    args.putInt(searchpage.ARG_SECTION_NUMBER, i + 1);
                    fragment.setArguments(args);
                    return fragment;
                case 1:
                    fragment = new newfeedpage();
                    args = new Bundle();
                    args.putInt(newfeedpage.ARG_SECTION_NUMBER, i + 1);
                    fragment.setArguments(args);
                  return fragment;
                default:
                    fragment = new profilepage();
                    args = new Bundle();
                    args.putInt(profilepage.ARG_SECTION_NUMBER, i + 1);
                    fragment.setArguments(args);
                  return fragment;
            }
        }

        @Override
        public int getCount() {
            return 3;
        }
        @Override
        public CharSequence getPageTitle(int position) {
            return "Section " + (position + 1);
        }

//        @Override
//        public boolean isViewFromObject(View view, Object object) {
//            return false;
//        }
    }


    private class searchpage extends Fragment {
        public static final String ARG_SECTION_NUMBER = "section_number";

        @Override
        public View onCreateView(LayoutInflater inflater, ViewGroup container,Bundle savedInstanceState) {
            View rootView = inflater.inflate(R.layout.layout2, container, false);


            return rootView;
        }
    }

    private class newfeedpage extends Fragment {
        public static final String ARG_SECTION_NUMBER = "section_number";

        @Override
        public View onCreateView(LayoutInflater inflater, ViewGroup container, Bundle savedInstanceState) {
            View rootView = inflater.inflate(R.layout.activity_main, container, false);
            return rootView;
        }
    }

    private class profilepage extends Fragment {
        public static final String ARG_SECTION_NUMBER = "section_number";

        @Override
        public View onCreateView(LayoutInflater inflater, ViewGroup container, Bundle savedInstanceState) {
            View rootView = inflater.inflate(R.layout.activity_main, container, false);
            return rootView;
        }
    }
}
